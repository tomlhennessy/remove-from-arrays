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
```

## hipsterfy
Takes in a sentence string and returns the sentence where every word is missing its last vowel

```javascript
let removeLastVowel = function(word) {
    let vowels = 'aeiou';

    for (let i = word.length - 1; i >= 0; i++) {
        let char = word[i];
        if (vowels.includes(char)) {
            return word.slice(0, i) + word.slice(i + 1);
        }
    }
    return word;
}

let hipsterfy = function(sentence) {
    // initialise array to store modified words
    let newWords = [];
    // split input sentence into array of words

    // iterate through each word in array
    for (let i = 0; i < words.length; i++) {
        // store the current word
        let word = words[i];
        // call helper function to remove last vowel from word
        newWords.push(removeLastVowel(word));
    }
    // join modified words into a single sentence
    return newWords.join(' ');
}
```

## Same Char Collapse
Collapses identical characters in a string.

```javascript
function sameCharCollapse(str) {
    // initialise a flag to control the loop
    let reducible = true;

    // continue looping until reducible becomes false
    while (reducible) {
        // split the string into an array of characters
        let chars = str.split("");
        // reset reducible flag to false
        reducible = false

        // iterate through the characters array
        for (let i = 0; i < chars.length - 1; i++) {
            // if two consecutive characters are identical
            if (chars[i] == chars[i+1]) {
                // remove both characters from the array
                chars[i] = "";
                chars[i + 1] = "";
                // set reducible flage to true to indicate reduction occured
                reducible = true;
            }
        }
        // join modified characters array back into string
        str = chars.join("");
    }
    // return final collapsed string
    return str;
}
console.log(sameCharCollapse("zzzxaaxy"));  // "zy"
// because zzzxaaxy -> zxaaxy -> zxxy -> zy
console.log(sameCharCollapse("uqrssrqvtt")); // "uv"
// because uqrssrqvtt -> uqrrqvtt -> uqqvtt -> uvtt -> uv
```
