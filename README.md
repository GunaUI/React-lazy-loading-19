This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).
### React Lazy loading with suspense.
* Lazy loading is a concept of loading the file only when it is needed , this will create huge impact in performance.
* Instead of normal import , we could import the component just like below
```jsx
const Posts = React.lazy(() => import('./containers/Posts'));
```
* Important here : we should import only default export , named export are not supported.(Posts.js)
```jsx
export default posts;
```
### Rendering the lazy loading in route
```jsx
import React, { Component, Suspense } from 'react';

<Route
  path="/posts"
  render={() => (
    <Suspense fallback={<div>Loading...</div>}>
    <Posts />
    </Suspense>
  )}
/>
```
* Refer App.js ....