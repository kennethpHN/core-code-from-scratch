## Wednesday 03/08/22

**Kata - Valid Parentheses**

```javascript
function validParentheses(parens) {
  let counter = 0
  if(parens.length === 1){
    return false;
  } else if(parens.length === 0){
    return true;
  }
  parens.split('').every((parenthesis) =>{
    
      if(parenthesis === "("){
        counter++
      }
      if(parenthesis === ")"){
        counter--
      }
      if(counter < 0) {
        return false
      }else {
        return true
      }
  })
  if(counter === 0){
    return true;
  }else{
    return false;
  }
}
```

**Kata - Convert String To Camel Case**
```javascript
function toCamelCase(str){
  let result = str.split(/[-_]/);
  for(let i = 1; i< result.length; i++){
    result[i] = result[i].replace(/(\b[a-z])/g,(x)=>{return x.toUpperCase();});
  }
  return result.join('');
}
```

**Kata - Unique In Order**
```javascript
var uniqueInOrder=function(iterable){
  let array = [...iterable]
  let result = []
  for(let i = 0; i< array.length; i++){
    if(array[i] === array[i+1]){
      continue;
    }
    result.push(array[i]);
  }
  return result;
}
```
