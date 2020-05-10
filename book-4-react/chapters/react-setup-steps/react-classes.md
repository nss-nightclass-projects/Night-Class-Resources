# Update App.js
`create-react-app` made some assumptions on how we are going to write our React.  To correct this replace the entire contents of `App.js` with this:

```js
import React from 'react';
import './App.scss';

class App extends React.Component {
  render() {
    return (
      <div className="App">
        <h2>INSIDE APP COMPONENT</h2>
        <button className="btn btn-info"><i class="fas fa-rocket"></i></button>
      </div>
    );
  }
}

export default App;
```

[Return to Instructions](../react-setup.md)
