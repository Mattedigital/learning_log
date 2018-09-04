### MERN Stack setup

#### Create project directory:

`mkdir project_name`

Access project directory:

`cd project_name`

#### Install dependancies:

`npm i express mongoose passport passport-jwt jsonwebtoken body-parser bcryptjs validator`

Express: our main framework

Mongoose:  Used to interact / connect to mongo DB

Passport: Authentication

passport-jwt: for using json web tokens

jsonwebtoken: used to actually generate the token

body-parser: take in data through our request and do what we want with it

bcryptjs: ?

validator: for validation

#### Install dev dependencies:

`npm i -D nodemon`

Nodemon: ?

#### Create server/entry point file:

```js
const express = require('express');

const app = express();

app.get('/', (req, res) => res.send('Hello'));

const port = process.env.PORT || 5000;

app.listen(port, () => console.log(`Server running on port ${port}`));
```

Then in the terminal:

`node server`





