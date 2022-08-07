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
