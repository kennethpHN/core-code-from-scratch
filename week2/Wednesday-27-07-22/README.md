## Wednesday 27/07/22

**Char From ASCII Value**

```
function getChar(c){
  return String.fromCharCode(c);
}
```
**Binary addition**

```
function addBinary(a,b) {
  let c = a+b
  return c.toString(2);
}
```

**Student's Final Grade**
```
function finalGrade (exam,projects) {

  return exam>90 || projects>10?100:exam>75 && projects>=5?90:
  exam>50 && projects>=2?75:0
  
}
```
