## Monday 01/08/22

**Kata - Who likes it?**
```javascript
const likes = (names) => {
  if(names.length ===0){
    return "no one likes this";
  }
  if(names.length === 1)
    return `${names[0]} likes this`;
  if(names.length ===2)
    return `${names[0]} and ${names[1]} like this`;
  if(names.length ===3)
    return `${names[0]}, ${names[1]} and ${names[2]} like this`;
  if(names.length >3)
    return `${names[0]}, ${names[1]} and ${names.length -2} others like this`;
}
```

**Kata - Bit Counting
```javascript
function countBits(n) {
  let binary = Array.from(n.toString(2),Number);
  return binary.reduce(function(accumulator,n){
    return accumulator + n;
  });;
};
```
