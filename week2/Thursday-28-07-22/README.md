## Thursday 28/07/22

**Remove All Exclamation Marks From The End Of Sentence**
```javascript
function remove (string) {  
  for(let i = string.length-1; i >0;i--){
    if(string.charAt(i)=="!"&&string.charAt(i+1)==""){
      string = string.substring(0,i);
    }
  }
  return string;
}
```
**Vowel Remover**
```javascript
function shortcut (string) {
  let short="";
  for(let i = 0; i<string.length;i++){
    if(string.charAt(i)=="a"||string.charAt(i)=="e"||string.charAt(i)=="i"
       ||string.charAt(i)=="o"||string.charAt(i)=="u"){
      continue;
    }
    short=short.concat(string.charAt(i));
  }
  return short;
}
```
