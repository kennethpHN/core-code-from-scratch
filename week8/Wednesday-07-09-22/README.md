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

[**Kata - Find The Odd Int**](https://www.codewars.com/kata/54da5a58ea159efa38000836/train/typescript)
```typescript
export const findOdd = (xs: number[]): number => {
   let counter = 1;
  for(let i = 0; i < xs.length; i++){
      if(i > xs.indexOf(xs[i])) continue;
      for(let j = i+1; j < xs.length; j++){
         if(xs[i]===xs[j]){
            counter++};
      }
      if(counter % 2 != 0){
         return xs[i];
      } else {
         counter = 1;
         };
  }
  return 0;
};
```

[**Kata - Which Are In?**](https://www.codewars.com/kata/550554fd08b86f84fe000a58/train/typescript)
```typescript
export function inArray(a1: string[], a2: string[]): string[] {
   let r: string[]=[];
   for(let i =0; i < a2.length; i++){
      for(let j =0; j < a1.length; j++){
         if(a2[i].includes(a1[j])){
            if(r.indexOf(a1[j])!=-1){
               continue;
            } else r.push(a1[j]);
         }
      }
   }
   return r.sort();
}
```
