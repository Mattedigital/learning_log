#### React

Stateless functions should always be pure functions.

Always declare Proptypes, this will aid debugging if wrong proptype is passed to component. It equally useful for future development to understand what props are required & what type of props should be passed in.

```js
import PropTypes from 'prop-types';

const ComponentName = props => (
    <h3>Showing results for {props.searchTerm}</h3>
);

ComponentName.propTypes = {
    searchTerm: PropTypes.string.isRequired,
};
```



