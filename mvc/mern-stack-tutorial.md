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

bcryptjs: hashing system for passwords

validator: for validation

#### Install dev dependencies:

`npm i -D nodemon`

Nodemon: Nodemon is a utility that will monitor for any changes in your source and automatically restart your server. Perfect for development. I

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
  mongoURI: 'mongodb://yourusername:yourpassword@ds115625.mlab.com:15625/devconnector'
}
```

#### Connect MongoDB with Moongoose in server.js:

Require Mongoose:

```js
const mongoose = require('mongoose');
```

Require database config \(the keys file we just created\):

```js
const db = require('./config/keys').mongoURI;
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
const db = require('./config/keys').mongoURI;

//Connect to MongoDB
mongoose
  .connect(db)
  .then(() => console.log('MongoDB Connected'))
  .catch(err =>  console.log(err));

app.get('/', (req, res) => res.send('Hello!!!!'));

const port = process.env.PORT || 5000;

app.listen(port, () => console.log(`Server runnning on port ${port}`));
```

#### Create Express routes:

Create a folder at root directory named 'routes' & cd in:

`mkdir routes`

`cd routes`

Create another directory named 'api':

`mkdir api`

Create files as follows:

`touch users.js` - controls authentication, login etc.

`touch profile.js` - to fetch user profile such as bio, location, website url.

`touch posts.js` - so users can create posts.

#### Require routes in server.js:

Include these files in the server.js before the express app is declared:

```js
const users = require('./routes/api/users');
const profile = require('./routes/api/profile');
const posts = require('./routes/api/posts');

const app = express();

...
```

#### Include routes in server.js:

Include routes above the port declaration:

```js
...

app.use('/api/users', users);
app.use('/api/profile', profile);
app.use('/api/posts', posts);

const port = process.env.PORT || 5000;

...
```

#### Update users.js, profile.js & posts.js route files:

Include express & router, then add route & export:

```js
const express =  require('express');
const router = express.Router();

router.get('/test', (req, res) => res.json({msg: "Users works"}));

module.exports = router;
```

Do the same for profile.js & posts.js but change the msg to correspond to the file name.

Navigating to `localhost:5000/api/users/test` should give json with the above `msg` text included. You can check this with profile & post URL's too.

Add comments for clarity, where the route goes, route description & who can access:

```js
...

// @route   GET api/posts/test
// @desc    Tests post route
// @access  Public
router.get('/test', (req, res) => res.json({msg: "Users works"}));

...
```

#### Create User model & Schema:

Create a new route directory titled models. Inside that directory create a file names User.js. Naming conventions for models are singular & capitalised. Hence User.js.

We need to create a users properties. Here we have name, email, password, avatar & date. All are mandatory apart from date which has a default value of `Date.now`.

```js
const mongoose = require('mongoose');
const Schema = mongoose.Schema;

// Create Schema
const UserSchema = new Scheam({
  name: {
    type: String,
    required: true
  },
  email: {
    type: String,
    required: true
  },
  password: {
    type: String,
    required: true
  },
  avatar: {
    type: String,
    required: true
  },
  date: {
    type: Date,
    default: Date.now
  }
});
```

We then need to export this using User as a variable name. Passing 'user' as the name we'd like to use & the Schema we just created, UserSchema:

```js
...

module.exports = User = mongoose.model('users', UserSchema);
```

#### User Registration & Postman:

Download [Postman](https://www.getpostman.com/).

You can now test `http://localhost:5000/api/users/test` using the GET request & get the message we applied earlier - Users works. Here's a screenshot:

![](/assets/Screen Shot 2018-10-29 at 09.05.41.png)Now we wish to create a register route. In `/routes/api/users.js` require the users model.

```js
...

// Load User model
const User = require('../../models/User');

...
```

Now we can create a new route that has access to this model & any mongoose methods:

```js
// @route   GET api/users/register
// @desc    Register userr
// @access  Public
router.post('/register', (req, res) => {
  User.findOne()
});
```

Note findOne, this is a mongoose method. When we send data to a route, such as a form in our application, we access it through `req.body`.

In order to do this we need to require `body-paser` in our `server.js` file & add some middleware. So in server.js this is what the top of your file should look like:

```js
const express = require('express');
const mongoose = require('mongoose');
const bodyParser = require('body-parser');

const users = require('./routes/api/users');
const profile = require('./routes/api/profile');
const posts = require('./routes/api/posts');

const app = express();

// Body parser middleware
app.use(bodyParser.urlencoded({ extended: false }));
app.use(bodyParser.json());
```

This allows us to access req.body.whatever.

GOT UP TO USER REGISTRATION & POSTMAN



Look into:

middleware - definition, where in project should middleware be defined.

jwt \(json web token\) vs google, fb, twitter oauth etc

