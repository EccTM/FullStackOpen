# **Part 1**

## **Exercises**

### **1.1:** Course Information, Step 1

I used create-react-app to initialize a new application. I then modified `index.js` to match the following:

```jsx
import React from 'react'
import ReactDOM from 'react-dom/client'

import App from './App'

ReactDOM.createRoot(document.getElementById('root')).render(<App />)
```

and `App.js` to match the following:

```jsx
const App = () => {
  const course = 'Half Stack application development'
  const part1 = 'Fundamentals of React'
  const exercises1 = 10
  const part2 = 'Using props to pass data'
  const exercises2 = 7
  const part3 = 'State of a component'
  const exercises3 = 14

  return (
    <div>
      <h1>{course}</h1>
      <p>
        {part1} {exercises1}
      </p>
      <p>
        {part2} {exercises2}
      </p>
      <p>
        {part3} {exercises3}
      </p>
      <p>Number of exercises {exercises1 + exercises2 + exercises3}</p>
    </div>
  )
}

export default App
```

I removed the extra files: `App.css, App.test.js, index.css, logo.svg, setupTests.js, reportWebVitals.js`

I refactored the code of `App.js` so that it consists of three new components: `Header`, `Content`, and `Total`.

All const data still resides in the `App` component, which passes the necessary data to each component using props.

`Header` takes care of rendering the name of the course, `Content` renders the parts and their number of exercises and `Total` renders the total number of exercises.

The `App` component's body is approximately as follows:

```jsx
const App = () => {
  // const-definitions

  return (
    <div>
      <Header course={course} />
      <Content ... />
      <Total ... />
    </div>
  )
}
```

I also removed the `.git` folder in the root of the project to avoid clashing with my existing repository.
