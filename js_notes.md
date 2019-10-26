# My javascript notes

## How to use the sort function

given an array of items e.g `const arr = [1,2,0,1,3,5];`
we call `arr.sort((a,b) => a < b ? -1 : 1)` where `a` is the current item in the array and `b` is the next item in the array, we use the ternary operator to give the condition that `if the current item is less than the next item then return -1 that is do not swap, but if it is less return 1 that is swap them`

## How to use filter function

given an array of items e.g `const arr = [1,2,3,5,6,7];` calling the filter function on the array returns a new array of items that passed the filter condition example is

```js
const arr = [1,2,3,4,5,6];

const filteredArray =  arr.filter((item) => {
    return item < 3;
});
// notice we returned a boolean which returns the current element if it passes the test
```
