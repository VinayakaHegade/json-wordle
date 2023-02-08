# wordle-mock-api

#### Prerequisite
* Create a folder
```
mkdir wordle-mock-api
cd wordle-mock-api
```

#### Step 1: Create a node js project
```
npm init -y
```

#### Step 2: Install json server dependency
```
npm i json-server
```

#### Step 3: Create server.js
```js
const jsonServer = require('json-server')

const server = jsonServer.create()

const router = jsonServer.router('db.json')
const middlewares = jsonServer.defaults()
 
server.use(middlewares)
server.use('/api', router)
server.listen(process.env.PORT || 5000, () => {
  console.log('JSON Server is running')
})


```


#### Step 4: Create db.json
```js
{
  "letters": [
    { "key": "a" },
    { "key": "b" },
    { "key": "c" },
    { "key": "d" },
    { "key": "e" },
    { "key": "f" }
  ],
  "solutions": [
    {
      "id": 1,
      "word": "cigar"
    },
    {
      "id": 2,
      "word": "rebut"
    },
    {
      "id": 3,
      "word": "sissy"
    },
  ]
}
```

#### Step 5: Run the Node JS Project
```
node server.js
```

#### Step 6: Test - List letters API 
```
http://localhost:5000/letters
```

Output:
```js
[
 {
    "key": "a"
  },
  {
    "key": "b"
  },
  {
    "key": "c"
  },
]
```

#### Step 7: Test - View Solutions Details API 
```
http://localhost:5000/solutions
```

Output:
```js
[
  {
    "id": 1,
    "word": "cigar"
  },
  {
    "id": 2,
    "word": "rebut"
  },
  {
    "id": 3,
    "word": "sissy"
  },
]
```
