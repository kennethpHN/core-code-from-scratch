## Thursday 04/08/22

**Kata - Fold An Array**
```javascript
function foldArray(array, runs)
{
  let folds = array;
  let middle = 0;
  let result= []
  for(let i = 1; i<=runs; i++)
  {
    result = [];
    switch(folds.length%2){
    case 1:
        middle = (Math.round(folds.length/2))-1;
        for(let i = middle+1; i<folds.length; i++){
          result.push(folds[middle-(i-middle)]+folds[i]);
        }
        result.push(folds[middle]);
        folds = [...result];
        break;
    case 0:
        middle=((folds.length/2)-1);
        for(let i = folds.length-1; i>middle; i--){
          result.push(folds[(folds.length-1)-i]+folds[i]);
        }
        folds = [...result];
        break;
    default:
        break;
  }}
  return folds;
}
```
