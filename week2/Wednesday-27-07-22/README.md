## Wednesday 27/07/22

**Kata - Char From ASCII Value**

```Javascript
function getChar(c){
  return String.fromCharCode(c);
}
```
**Kata - Binary addition**

```javascript
function addBinary(a,b) {
  let c = a+b
  return c.toString(2);
}
```

**Kata - Student's Final Grade**
```javascript
function finalGrade (exam,projects) {

  return exam>90 || projects>10?100:exam>75 && projects>=5?90:
  exam>50 && projects>=2?75:0
  
}
```
