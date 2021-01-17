### type 类型别名（为类型取一个名字）
```typescript
const add: (x: number, y: number) => number = (a, b) => (a + b);

// 等价于

interface Add {
    (x: number, y: number): number
}

// 
type Add = (x: number, y: number) => number
```
