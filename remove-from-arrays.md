# Remove From Array

```javascript
function removeFromArray(location, arr) {
    // check the value of the location parameter
    if (location == "FRONT") {
        // remove first element
        arr.shift();
    } else if (location == "BACK") {
        // remove last element
        arr.pop();
    } else {
        console.log("ERROR");
    }
}

testArray = [0,1,2,3,4]

removeFromArray("FRONT", testArray)
console.log(testArray) // [1,2,3,4]

removeFromArray("BACK", testArray)
console.log(testArray) // [1,2,3]

removeFromArray("MIDDLE", 4, testArray) // "ERROR"
console.log(testArray) // [1,2,3]
```

## Popper
Takes in an array and a number as args. Function should remove the last num elements from the array, mutating the original array. Should return a new array containing elements that were removed.

```javascript
let popper = function(array, num) {
    // initialise empty array to store removed elements
    let removed = [];

    // remove 'num' elements from end of array
    for (let i = 0; i < num; i++) {
        // remove last element from array
        let el = array.pop();
        // add removed element to the 'removed' array
        remove.push(el);
    }
    // return array containing removed elements
    return removed;
}

let arr1 = ['a', 'b', 'c', 'd', 'e'];
console.log(popper(arr1, 2)); // [ 'e', 'd' ]
console.log(arr1); // [ 'a', 'b', 'c' ]
```

## Rotate Right
Function takes in two parameters: array (the array to rotate) and num (the number of positions to totate the array).

```javascript
let rotateRight = function(array, num) {
    // create copy of original array
    let copy = array.slice();

    // iterate 'num' times
    for (let i = 0; i < num; i++) {
        // remove last element and store it in 'el'
        let el = copy.pop();
        // add removed element to beginning
        copy.unshift(el);
    }
    // return rotated copy of the array
    return copy;
}

let animals = ['wombat', 'koala', 'opossum', 'kangaroo'];
console.log(rotateRight(animals, 3)); // [ 'koala', 'opossum', 'kangaroo', 'wombat' ]
console.log(animals); // [ 'wombat', 'koala', 'opossum', 'kangaroo' ]
```

## Rotate
rotates an array either to the left or the right depending on the value of the 'num' parameter.

```javascript
let rotate = function(array, num) {
    // check if num is positive (rotate right) or negative (rotate left)
    if (num > 0) {
        // rotate right
        for (let i = 0; i < num; i++) {
            // remove last element and store it in 'el'
            let el = array.pop();
            // add removed element to beginning of array
            array.unshift(el);
        }
    } else {
        // rotate left
        // convert negative num to positive equivalent
        for (let i = 0; i < -(num); i++) {
            // remove first element and store it in 'el'
            let el = array.shift()
            // add removed element to end of array
            array.push(el);
        }
    }
}
