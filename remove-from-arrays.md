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
