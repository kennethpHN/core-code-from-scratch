## Tuesday 02/08/22

**Kata - Simple Pig Latin**
```javascript
function pigIt(str){
  let text = str.split(' ');
  for(let i = 0;i<text.length;i++){
    if(!/[^\w]/.test(text[i])){
      text[i] = text[i].slice(1) + text[i][0] + 'ay';
    } 
  }
  return text.join(' ');
}
```

