## Thursday 28/07/22

**Remove All Exclamation Marks From The End Of Sentence**
```
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
```
```
