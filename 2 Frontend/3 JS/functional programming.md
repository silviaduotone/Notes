# functional programming

## Map

The `**map()**` method **creates a new array** with the results of calling a provided function on every element in the calling array.

Since `map` builds a new array, ** using it when you aren't using the returned array is an anti-pattern**; use [`forEach`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach) or [`for-of`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of) instead. Signs you shouldn't be using map: A) You're not using the array it returns, and/or B) You're not returning a value from the callback.


```js
    var animals = [
      {name:"kitty", species:"cat"},
      {name:"kette", species:"dog"},
      {name:"mitty", species:"cat"},
      {name:"metty", species:"fish"}
    ]
    
    // whatis is a new array!
    var whatis = animals.map(x => x.name + " is a " + x.species);

```
```js
var numbers = [1, 4, 9];
var roots = numbers.map(function(num) {
return Math.sqrt(num)
});
// roots is now [1, 2, 3]
// numbers is still [1, 4, 9]
```

