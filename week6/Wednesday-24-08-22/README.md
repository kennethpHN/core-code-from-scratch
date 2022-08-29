## Wednesday 24/08/22

[**Kata - A Rule of Divisibility by 13**](https://www.codewars.com/kata/564057bc348c7200bd0000ff/train/typescript)
```typescript
export function thirt(n: number): number {
  let array: number[]= n.toString().split('').map((i) => Number(i)).reverse();
  let stationary: number = 0;
  let pattern: number[] = [1, 10, 9, 12, 3, 4];
    for(let x:number=0;x<array.length;x++)
  {
    stationary += array[x]*pattern[x%6];
  }
  return stationary === n? stationary: thirt(stationary);
}

```
