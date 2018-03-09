Gotchas

Easiest / Less frustrating approach:

1. Create folder structure.
2. Then create routes.
3. Then build the individual components.

Further reading on the mental model required to build React apps with ease - [https://reactjs.org/docs/thinking-in-react.html](https://reactjs.org/docs/thinking-in-react.html)

Read on Sippers & Loading UI for pending API calls - [https://www.robinwieruch.de/react-fetching-data/](https://www.robinwieruch.de/react-fetching-data/)

Example Routes in App.js:

```js
const App = ({ match }) => (
  <div className='container'>
    <h1>Matte Fletcher | Boilerplate React Build</h1>
    <Router>
      <div>
        <Route exact path="/" component={Gallery} />
        <Route path="/a" component={ComponentA} />
        <Route path="/b" component={ComponentB} />
        <Route path="/:userId" component={GalleryItemView} />
      </div>
    </Router>
  </div>
)
```

BrowserRouter required for history \(even if not declared like a component would be\).

```js
import { BrowserRouter as Router, Route } from 'react-router-dom';
```

{match.url} is only needed for nested routes ie /tacos/chicken & tacos/beef \(where beef & chicken are nested\). not needed if not nested ie /beef, /chicken.

```js
<Route path={`${match.url}/:id`} component={GalleryItemView} />
```



