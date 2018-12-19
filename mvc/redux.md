### Redux

**Key takeaways:**

**createStore\(\) from redux is what is required to create/initiate a redux store.**

**Reducers produce the state of our application.**

**Reducers take two parameters: the current state & an action.**



[react-redux-tutorial-beginners](https://www.valentinog.com/blog/react-redux-tutorial-beginners/)

**Import Redux:**

In your React development environment and install Redux:

```js
npm i redux --save-dev
```

**Creating a store:**

```js
mkdir -p src/js/store
```

Create a new file named `index.js` in `src/js/store` and finally initialize the store:

```js
// src/js/store/index.js

import { createStore } from "redux";
import rootReducer from "../reducers/index";
const store = createStore(rootReducer);
export default store;
```

`createStore` is the function for creating the Redux store.

`createStore` takes a reducer as the first argument, `rootReducer` in our case.

You may also pass an initial state to `createStore`. But most of the times you don’t have to. Passing an initial state is useful for server side rendering \(SSR\). Anyway, the state comes from reducers.

In Redux** reducers produce the state of the application**.

**Reducers:**

A reducer is a Javascript function. **Reducers take two parameters: the current state & an action.**

Create a root reducer:

```js
mkdir -p src/js/reducers
```

Then create a new file `index.js` in `src/js/reducers`. Add the following:

```js
const initialState = {
 articles: []
}

const rootReducer = (state = initialState, action) => state;

export default rootReducer;
```

This reducer does nothing but return the initial state. No actions take place.

**Actions:**  
We create a new store state by dispatching an action. Note we do not update the state, we copy the current state plus the new data, this is because the state is immutable.

This is what an action looks like:

```js
{
 type: 'ADD_ARTICLE',
 payload: { name: 'Redux tutorial', id: 1 }
}
```

It's just a js object! Every action requires a type property to describe how the state should change. The payload here is a new article which will be added to the current state when called.

It is best practice to wrap every action within a function. These functions are called action creator.

Let's put it all together.

Create an actions directory

```js
mkdir -p src/js/actions
```

Create a new file named `index.js`:

```js
export const addArticle = article => ({
 type: "ADD_ARTICLE",
 payload: article
});
```

The type property is just a string. This string is used to determine the next state. Use CONSTANTS to help avoid errors.

Create a constants directory:

```js
mkdir -p src/js/constants
```

Create a new file named `action-types.js`:

```js
export const ADD_ARTICLE = "ADD_ARTICLE"
```

Now update `src/js/actions/index.js` to use action types:

```js
import { ADD_ARTICLE } from "../constants/action-types";

export const addArticle = article => ({
 type: ADD_ARTICLE,
 payload: article
});
```

**Refactoring our reducer:**

