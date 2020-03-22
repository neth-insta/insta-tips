# Sum from array value
```javascript
/** Option 1 */
function sum(...args){
  var total;
  total = args.reduce((acc,elem)=> acc+elem,0);
  console.log(total);
}
sum(1,2,3);

/** Option 2 */
function sum(args){
  var total;
  total = args.reduce((acc,elem)=> acc+elem,0);
  console.log(total);
}
sum([1,2,3,4]);
```
