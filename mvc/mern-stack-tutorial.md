### MERN Stack Project

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

Navigate to [http://localhost:5000/](http://localhost:5000/) & see the string 'Hello'. Note if you resave the file no changes take effect.

How do we make chnages without having to restart the server?

#### Add scripts to package.json:

```js
"scripts": {
    "start": "node server.js",
    "server": "nodemon server/js"
 },
```

Now run  `npm run server` & notice the ability to make changes which take effect on page reload.

#### Create a new directory at root level:

`mkdir config`

`cd config`

`touch keys`

Add the mLab user URI to your keys file:

```js
module.exports = {
  mongoURI: 'mongodb://matte:Artojoblw1@ds115625.mlab.com:15625/devconnector'
}
```

#### Connect MongoDB with Moongoose in server.js:

Require Mongoose:

```js
const mongoose = require('mongoose');
```

Require database config \(the keys file we just created\):

```js
const db = require('./config').mongoURI;
```

Connect to MongoDB:

```js
mongoose
  .connect(db)
  .then(() => console.log('MongoDB Connected'))
  .catch(err =>  console.log(err));
```

End server.js file looks like this:

```js
const express = require('express');
const mongoose = require('mongoose');

const app = express();

//DB config
const db = require('./config').mongoURI;

//Connect to MongoDB
mongoose
  .connect(db)
  .then(() => console.log('MongoDB Connected'))
  .catch(err =>  console.log(err));

app.get('/', (req, res) => res.send('Hello!!!!'));

const port = process.env.PORT || 5000;

app.listen(port, () => console.log(`Server runnning on port ${port}`));
```


