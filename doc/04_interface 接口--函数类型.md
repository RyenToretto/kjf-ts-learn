### 定义函数类型的接口
```typescript
const add: (x: number, y: number) => number = (a, b) => (a + b);

// 等价于

interface Add {
    (x: number, y: number): number
}
```
