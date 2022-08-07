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
**Kata - Counting Duplicates**
```javascript
function duplicateCount(text){
  text = text.toLowerCase().split('').sort();
  let count = 0;
  for(let i =0; i< text.length; i++){
    if(text[i]===text[i+1]){
      count++
      i= text.lastIndexOf(text[i]);
    }
  }
  return count;
}
```

**Kata - Decode The Morse Code**
```javascript
decodeMorse = function(morseCode){
  let words = morseCode.trim().split(' ')
  
  let result = []
  for(let i = 0; i < words.length; i++){
    if(words[i]===""&&words[i+1]===""){
      result.push(" ")
      continue;
    }
    result.push(MORSE_CODE[words[i]]);
  }
  
  return result.join('');
}
```

