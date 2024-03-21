# Express #
- Hello world server -
```
const express = require('express')
const app = express()
const port = 5000

app.get('/', (req, res) => {
    res.send("Hello World!")
})

app.listen(port, () => {
    console.log(`Server running on port: ${port}`)
})
```
- Get the headers - `req.headers`
- Get specific header value - `req.headers["Auth"]`
- Express doesn't have utility to get the body, so we use another module `bodyparser` -
```
const bodyParser = require("body-parser")

// middleware
// we can also use express.json()
app.use(bodyParser.json())

// finally to get the body
req.body
```
- Get query parameters - `req.query`
- Get url parameters - 
```
app.get('/files/:fileName', (req, res) => {
    const fileName = req.params.fileName
})
```
- Sending json response - `res.json(obj)`. `obj` is a JS object.