### Redux

[https://hackernoon.com/a-basic-react-redux-introductory-tutorial-adcc681eeb5e](https://hackernoon.com/a-basic-react-redux-introductory-tutorial-adcc681eeb5e)

The **key components **of a React+Redux App are the following:

1. Reducers - A reducer is a function that returns a piece of the application state
2. Containers - A container wraps a React component and makes available to him the piece of state we need to pass to it as props inside the component.
3. Actions \(and ActionCreators\) - returns a new copy of the state modified \(or not\).

We must have a _”RootReducer” that is the combination of all the reducers of our application \(our application state / Redux Store_\). For that, Redux offers the combineReducers function.

**When a component needs to know about a particular piece of state from our **_**Redux Store**_**, then it needs to be a container.**

To connect a Component with the _Redux Store_, we need to import the connect function from react-redux library and pass it some parameters to be described.

