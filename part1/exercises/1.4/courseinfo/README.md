# **Part 1**

## **Exercises**

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
