# Sum Plus & Minus form Array
```javascript
/** Option 1 */
function sumPlusMinus(...arr){
  return arr.reduce(
    (acc, elem)=>({
      plus: elem > 0 ? acc.plus + elem : acc.plus,
      minus: elem < 0 ? acc.plus + elem : acc.minus
    }),
    {plus:0, minus:0}
  );
}
console.log(sumPlusMinus(1,1,1,-2,-2,-2));

/** Option 2 */
function sumPlusMinus(arr){
  return arr.reduce(
    (acc, elem)=>({
      plus: elem > 0 ? acc.plus + elem : acc.plus,
      minus: elem < 0 ? acc.plus + elem : acc.minus
    }),
    {plus:0, minus:0}
  );
}
console.log(sumPlusMinus([1,1,1,-2,-2,-2]));
```
