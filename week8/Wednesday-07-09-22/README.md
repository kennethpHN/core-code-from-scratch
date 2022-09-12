## Wednesday 07/09/22

[**Kata - Make the Deadfish Swim**](https://www.codewars.com/kata/51e0007c1f9378fa810002a9/train/typescript)
```typescript
export function parse(data: string): number[] {
   let result: number[] = [];
   let op: number = 0;
   data.split('').forEach(
      x =>{
         switch(x){
            case 'i' :
              op++;
            break;
            case 'd' :
              op--;
            break;
            case 's' :
              op = Math.pow(op,2);
            break;
            case 'o' :
              result.push(op);
            break;
         }
   })
  return result;
}
```

[**Kata - Duplicate Encoder**](https://www.codewars.com/kata/54b42f9314d9229fd6000d9c/train/typescript)
```typescript
export function duplicateEncode(word: string) {
  let result: string[] = word.toLowerCase().split('');
  return result.map((x: string, index, word: string[]) => {return word.indexOf(x) === word.lastIndexOf(x) ? '(': ')';}).join('');
}
```
