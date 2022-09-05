## Wednesday 31/08/22

[**Kata - Build Tower**](https://www.codewars.com/kata/576757b1df89ecf5bd00073b/train/typescript)

```typescript
const towerBuilder = (nFloors: number): string[] => {
    let tower: string[] = [];
    for (let i = 0; i < nFloors; i++) {
        tower.push(" ".repeat(nFloors - i - 1) + "*".repeat((i * 2)+ 1) + " ".repeat(nFloors - i - 1))
    }
    return tower;
}
```
