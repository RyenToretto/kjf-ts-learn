### 举个例子说明，为何需要枚举类型：
    // 根据不同角色执，行不同的初始化
    function initSystem(role) => {
        if (role === 1 || role === 2) {
            // 是 1/2 角色
        } else if (role === 3 || role === 4) {
            // 是 3/4 角色
        } else if (role === 5) {
            // 是 5 这个角色
        } else {
            // 不存在的角色
        }
    }
    
    缺陷： 
        1. 可读性差，很难记住每个数字代表了什么
        2. 可维护性差，改一个地方，处处需要改
        3. 需要写注释，或者文档

### 枚举 （定义后的属性只读）
    可以理解为手机电话薄
    我们只需要记得人名就行，不用记每个人的电话号码是多少
```typescript
        enum RoleType {
            teacher = 1,
            master = 2,
            father = 3,
            mother = 4,
            student = 5
        }
        function initSystem(role) {
            if (role === RoleType.master || role === RoleType.teacher) {
                // 是 master/teacher 角色
            } else if (role === RoleType.father || role === RoleType.mother) {
                // 是 father/mother 角色
            } else if (role === RoleType.student) {
                // 是 student 这个角色
            } else {
                // 不存在的角色
            }
        }
```
数字枚举（存在
[反向映射](https://www.tslang.cn/play/index.html)
，成员和值 都被作为 key）
        
```javascript
        var RoleType;
        (function (RoleType) {
            RoleType[RoleType["teacher"] = 1] = "teacher";
            RoleType[RoleType["master"] = 2] = "master";
            RoleType[RoleType["father"] = 3] = "father";
            RoleType[RoleType["mother"] = 4] = "mother";
            RoleType[RoleType["student"] = 5] = "student";
        })(RoleType || (RoleType = {}));
```
    字符串枚举（不可以反向映射）
    异构枚举（容易引起混淆，不建议使用）
       
