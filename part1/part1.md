# **Part 1:** Introduction to React

## **Lessons**

- **A:** Introduction to React
- **B:** Javascript
- **C:** Component State, Event Handlers
- **D:** More Complex States, Debugging React Apps

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

### **1.2:** Course Information, Step 2

I have refactored the Content component so that it does not render any names of parts or their number of exercises by itself. Instead it only renders three Part components of which each renders the name and number of exercises of one part.

```jsx
const Content = ... {
  return (
    <div>
      <Part .../>
      <Part .../>
      <Part .../>
    </div>
  )
}
```

### **1.3:** Course Information, Step 3

I modified the variable definitions of the `App` component as follows and also refactored the application so that it still works:

```jsx
const App = () => {
  const course = 'Half Stack application development'
  const part1 = {
    name: 'Fundamentals of React',
    exercises: 10
  }
  const part2 = {
    name: 'Using props to pass data',
    exercises: 7
  }
  const part3 = {
    name: 'State of a component',
    exercises: 14
  }

  return (
    <div>
      ...
    </div>
  )
}
```

### **1.4:** Course Information, Step 4

I then placed the objects into an array by modifying the variable definitions of `App` into the following form, and modified the other parts of the application accordingly:

```jsx
const App = () => {
  const course = 'Half Stack application development'
  const parts = [
    {
      name: 'Fundamentals of React',
      exercises: 10
    },
    {
      name: 'Using props to pass data',
      exercises: 7
    },
    {
      name: 'State of a component',
      exercises: 14
    }
  ]

  return (
    <div>
      ...
    </div>
  )
}
```

At this point I am assuming that there are always three items, so I don't need to go through the array using loops.

I also avoid passing the different objects as separate props from the `App` component to the components `Content` and `Total` and instead, pass them directly as an array:

```jsx
const App = () => {
  // const definitions

  return (
    <div>
      <Header course={course} />
      <Content parts={parts} />
      <Total parts={parts} />
    </div>
  )
}
```

### **1.5:** Course Information, Step 5

Taking the changes one step further, I changed the course and its parts into a single JavaScript object, and fixed references to everything that changed.

```jsx
const App = () => {
  const course = {
    name: 'Half Stack application development',
    parts: [
      {
        name: 'Fundamentals of React',
        exercises: 10
      },
      {
        name: 'Using props to pass data',
        exercises: 7
      },
      {
        name: 'State of a component',
        exercises: 14
      }
    ]
  }

  return (
    <div>
      ...
    </div>
  )
}
```
