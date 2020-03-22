# Sum from array value
```javascript
function sum(...args){
  var total;
  total = args.reduce((acc,elem)=> acc+elem,0);
  console.log(total);
}

sum(1,2,3);

sum(1,2,3,4);
```
