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

[**Kata - Meeting**](https://www.codewars.com/kata/59df2f8f08c6cec835000012/train/typescript)
```typescript
export function meeting(s: string): string {
    let list: string[] = s.split(';')
        let map1 = list.map(x => x.toUpperCase().split(':').reverse().join(', ')).sort();
        let map2 = map1.map(x => x = `(${x})`).join('');
    return map2;
}
```
