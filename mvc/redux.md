### Redux

[https://hackernoon.com/a-basic-react-redux-introductory-tutorial-adcc681eeb5e](https://hackernoon.com/a-basic-react-redux-introductory-tutorial-adcc681eeb5e)

**Key principles of redux:**

1. The state is only ever read only.
2. The state can only ever be changed by dispatching an action. e.g INCREMENT, DECREMENT or ADD\_COMMENT
3. To describe state mutations you have to write a function that takes the previous state of the app, the action being dispatched  & returns the next state of the app. This function needs to be a pure function. This function is called the reducer.



**Most commonly used redux methods:**

1. `.getState()` returns the current state of the redux store.
2. `.dispatch({type: 'INCREMENT'})` allows you to dispatch actions to change the state of your application.
3. `.subscribe()` allows you to register a callback for anytime a redux action has been dispatched.



```
// import createStore
import { createStore } from 'Redux';

// create a reducer function
const counter = (state = 0, action) => {
    switch (action.type) {
        case 'INCREMENT':
            return state + 1;
        case 'DECREMENT':
            return state - 1;
        default:
            return state;
    }
}

// create the store
const store = createStore(counter);

const render = () => {
    document.body.innerText = store.getState();
}

store.subscribe(render);
render();
    
document.addEventListener('click', () => {
    store.dispatch({type: 'INCREMENT'})
});
```





