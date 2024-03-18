## Variables ##
- `let` and `var` are used to define variables and `const` is used to define a constant value.
- Variables declared by `var` keyword are scoped to the immediate function body (hence the function scope), whereas `let` variables are scoped to the immediate enclosing block denoted by { } (hence the block scope).

## Conditionals ##
- if-else -
```
if (condition) {
    ...
} else {
    ...
}
```

## Loops ##
- for-loop -
```
for (let i = 0; i <= 10; i++) {
    ...
}
```

## Functions ##
- Functions -
```
def sum(a, b) {
    return a + b;
}
```

- Callback functions - a callback is a function passed as an argument to another function -
```
def printConsole(data) {
    console.log("Result: " + data);
}

def sum(a, b, printFn) {
    let result = a + b;
    printFn(result);
}

sum(5, 10, printToConsole);
```

## String Manipulation ##
- String length - `str.length`
- Index of the first occurrence - `str.indexOf("World")`. Returns -1 if the substring is not present.
- Index of the last occurrence - `str.lastIndexOf("World")`
- Slice substring - `str.slice(0, 5)`. Returns substring from 0th to 4th index.
- Replace substring with another string - `str.replace(target, replacement)`
- Splitting the string - `str.split(" ")`. Returns array of strings split by whitespace character.
- Trimming the leading and trailing spaces - `str.trim()`
- Upper-case - `str.toUpperCase()`
- Lower-case - `str.toLowerCase()`
- Converting string to an int - `parseInt(str)` -
```
parseInt("42")  // returns 42
parseInt("42.5")    // returns 42
parseInt("42px")    // returns 42 - trailing strings are ignored
parseInt("hello42px")   // returns NaN - leading strings will return NaN
```

## Date Operations ##
- Consider current date is `2024-03-18`
- Create date instance - `const currDate = new Date()` - returns 2024-03-18 when printed.
- Get day of the month - `currDate.getDate()` - returns 18.
- Get month - `currDate.getMonth()` - returns 2 because months are zero-indexed. 
- Get (year - 1900) - `currDate.getYear()` - returns 134.
- Get year - `curr.getFullYear()` - returns 2024.
- Get hours, minutes and seconds - `currDate.getHours()`, `currDate.getMinutes()`, `currDate.getSeconds()`
- Get milliseconds since 1970 (aka epoch timestamp) - `currDate.getTime()`
- Setting components of the date - `currDate.setFullYear(2025)`

## Arrays ##
```
const ages = [21, 22, 23, 24, 25]
ages[1] // array indexing - returns 22
```

### Array Operations ###
- Append at the back (in-place) - `arr.push(2)`
- Pop from the back - `arr.pop()`
- Append at the front (in-place) - `arr.unshift(0)`
- Pop from the front - `arr.shift()`
- Concatenation (returns another array) - `arr1.concat(arr2)`

## Objects ## 
```
const user = {
    name: "Ishan",
    gender: "male"
}
user["name"]    // returns "Ishan"
user.name       // also returns "Ishan" - exactly same as previous
```

### Object Operations ###
- Get keys - `Object.keys(obj)`
- Get values - `Object.values(obj)`
- Get both list of keys and values as nested array (2D) - `Object.entries(obj)`
- Check if key is present - `obj.hasOwnProperty("key")`
- Add more key-value pairs - `Object.assign(obj, { newProperty: "newValue" })`. Note that we canuse it to merge any number of key-value pairs to the first object - `Object.assign(obj, { newProperty1: "newValue1" }, { newProperty2: "newValue2" })`

### Object <=> JSON String Conversion ###
- Parse string to object - `JSON.parse(str)`
- Convert object to string - `JSON.stringify(obj)`

# Class #
```
class Animal {
    constructor(name, legCount) {
        this.name = name
        this.legCount = legCount
    }

    static isLiving() {
        return True
    }

    describe() {
        return `${this.name} has ${this.legCount} legs`
    }
}

let dog = new Animal("dog", 4)
dog.describe()  // calling function on object
Animal.isLiving()   // static function call
```

