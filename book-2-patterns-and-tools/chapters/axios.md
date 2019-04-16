# Axios

## Using Axios
> For every file you will need to make an XHR request in, you will need to require Axios
```js
import axios from 'axios';

const examplePromise = () => new Promise((resolve, reject) => {
  axios.get('http://localhost:3001/example')
    .then((data) => {
      resolve(data);
    })
    .catch((error) => {
      reject(error);
    });
});
```