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
