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
