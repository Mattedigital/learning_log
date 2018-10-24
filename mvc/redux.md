### Redux

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

You may also pass an initial state to `createStore`. But most of the times you don’t have to. Passing an initial state is useful for server side rendering (SSR). Anyway, the state comes from reducers.

In Redux reducers produce the state. The state is not something you create by hand.

