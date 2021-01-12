### 举个例子说明，为何需要枚举类型：
只读属性
```typescript
interface Member {
    readonly id: string;
    name: string;
}

function renderMember(responseData: Member[]) {
    responseData.forEach(member => {
        console.log(member.id, member.name);
    })
}

const responseData = [
    { id: 1, name: '0a'},
    { id: 2, name: '2b'},
    { id: 3, name: '3c'}
]
renderMember(responseData);
```

### 类型断言
    明确的高速编译器，这个变量的类型
