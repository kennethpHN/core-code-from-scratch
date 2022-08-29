## Tuesday 23/08/22

[**Kata - Square(n) Sum**](https://www.codewars.com/kata/515e271a311df0350d00000f/train/typescript)

```typescript
export function squareSum(numbers: number[]): number {
  const initialValue: number = 0;
  const square: number = numbers.reduce(
  (previousValue:number, currentValue:number) => previousValue + currentValue**2,
  initialValue);
  return square;
}
```
[**Kata - A Wolf In Sheep's Clothing**](https://www.codewars.com/kata/5c8bfa44b9d1192e1ebd3d15/train/typescript)
```typescript
export function warnTheSheep(queue: string[]): string {
  if(queue[queue.indexOf("wolf")+1] === "sheep"){
    return "Oi! Sheep number "+(queue.length-(queue.indexOf("wolf")+1))+"! You are about to be eaten by a wolf!";
  }else return "Pls go away and stop eating my sheep";
}
```
