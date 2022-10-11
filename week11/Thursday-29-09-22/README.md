## Thursday 29/09/22

### Forrest Gump Ping-Pong API 🏓:

Create a simple REST API with which you can play ping-pong.

**API Requeriments:**

- Use Express JS to build the API.
- Use any port you want for the API.
- The API has to be able to respond to the "ping" request with the "pong" message.
- Use `/api/buba-gump` as the root route for the API.
- Make sure your API responds to the request using JSON e.g.:
  ```javascript
  {
    "message": "pong"
  }
  ```
- Use Postman to test your API.
- Optional but desirable, make your API capable of responding to any player move:
  - If the user makes the "ping" move, your API should respond with "pong".
  - If the user makes the "pong" move, your API should respond with "ping".
  
**Solution**

```javascript
const express = require('express');

const app = express()
const port = 3000

app.get('/api/buba-gump',(req,res)=> {
    res.send({"status":"OK"})
})

app.get('/api/buba-gump/ping', (req, res) => {
    res.send({"ping": "pong"})
  })

  app.get('/api/buba-gump/pong', (req, res) => {
    res.send({"pong": "ping"})
  })
 ```

### Delayed Response API ⏳:

Create a simple REST API that receives a request containing a number that represents a delay  
in milliseconds. The API should respond to the request after the delay specified
in the request has expired.

**API Requeriments:**

- Use Express JS to build the API.
- Use any port you want for the API.
- The API should use route parameters to get the desired delay:

  ```bash
    # Request example
    # Here 3000 indicates a delay of 3000 milliseconds
    http://localhost:3000/api/delay/3000
  ```

- Your API should have just one request handler.
- You can send any response you want after the delay has expired.
- If no delay is provided in the request, the API should use 1000 as default.

**Solution**

```javascript
const express = require('express')
const app = express()
const port = 3000

app.get('/api/delay/:numberId?', (req, res) => {

  console.log(req.params);
  if(typeof(req.params.numberId)==="undefined"){
    res.send("delay message of 1000 milliseconds")
  }
  else{
    setTimeout(()=>{res.send(`delay message of ${req.params.numberId} milliseconds`)},req.params.numberId)
  }


})

app.listen(port, () => {
  console.log(`App listening on port ${port}`)
})
```
