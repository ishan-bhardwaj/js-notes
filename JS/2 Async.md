## Promises ##
- Uses callbacks under the hood.
```
// Custom asynchronous function
function readCustomFile() { 
    return new Promise(function(resolve) {
        fs.readFile("file.txt", "utf-8", function(err, data) {
            resolve(data)
        })
    })
}

// callback function to call
function onComplete(data) {
    console.log(data)
}

readCustomFile().then(onComplete)
```
- `readCustomFile()` function will be called asynchronously and when it is completed, it will added into the Callback Queue. The main thread will pick up the result from the callback queue and calls `onComplete` function on it.
- `resolve(data)` fulfills the promise with the result.

## Async await ##
- Use callbacks/promises under the hood.
```
// Custom asynchronous function
function readCustomFile() { 
    return new Promise(function(resolve) {
        fs.readFile("file.txt", "utf-8", function(err, data) {
            resolve(data)
        })
    })
}

async function main() {
    let value_v1 = readCustomFile()    // returns Promise { result or <pending> }
    let value_v2 = await readCustomFile() // retuns the actual result
    console.log("waiting")
    console.log(value_v2)
}

main()
console.log("main thread")
```
- `main()` function gets called asynchronously and prints out `main thread` immediately. But `waiting` and the result will be printed one after the other and only when `readCustomFile()` is completed.