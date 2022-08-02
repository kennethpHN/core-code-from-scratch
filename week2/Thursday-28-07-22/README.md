## Thursday 28/07/22

**Kata - Remove All Exclamation Marks From The End Of Sentence**
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
**Kata - Vowel Remover**
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
**Kata - Rock Paper Scissors!**
```javascript
const rps = (p1, p2) => {
        if (p1 == "rock" && p2 == "scissors") {
          return "Player 1 won!";
        } 
        if (p1 == "rock" && p2 == "paper") {
          return "Player 2 won!";
        }
        if (p1 == "scissors" && p2 == "paper") {
           return "Player 1 won!";
        }
        if (p1 == "scissors" && p2 == "rock") {
          return"Player 2 won!";
        }
        if (p1 == "paper" && p2 == "rock") {
          return"Player 1 won!";
        }
        if (p1 == "paper" && p2 == "scissors") {
          return"Player 2 won!";
        }
        if (p1 == p2) {
          return"Draw!";
        }
};
```
**Kata - Persistent Bugger**
```javascript
function persistence(num) {
  let sp = (''+num).split("")
  let sum=1;
  if(parseInt(sp.join(""))<10){
    return 0;
  }
  for(let i = 0; i<sp.length;i++){
    sum *= parseInt(sp[i]);
  }
  return 1 + persistence(sum)
}
```
