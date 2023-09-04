# Notes for Modern React Course

# What is React?

- Display HTML for users and changes HTML as user does something
- React is a 'wrapper' around HTML.
- JSX is not valid JavaScript code.
- Dev Server: Runs Babel and Webpack which creates a bundle.js file. bundle.js contains all Javascript code.

## How does a React App start up?

- App makes request and Server responses with index.html file. index.html file loaded in browser. index.html contains additional scripts to load additional code for React app.
- App makes second request to Server and gets bundle.js file. bundle.js references 'root' div.
- React takes control of 'root' div.

# Creating content with JSX

## Rules for converting HTML to JSX

1. All prop names follow camelCase
2. Number attributes use curly braces
3. Boolean 'true' can be written with just the property name. 'False' should be written with curly braces.
4. The 'class' attribute is writen as className.
5. In-line syles are provided as objects.

## Module system overview

- Import/Export system allow modules to share variables
  Basic Rules

1. Export statements make variables to other file

- default export: only one export per file. Default exports can be renamed in the importing file. Example `export default App`
- named export: use when exporting multiple variables, can have as maany named export as we want. Example with export and import `export const message = 'hi'` / `import {message} from './App`.

2. No `./` means imported from library. Example `import React from react`

3. `../` denotes how far 'unnested' the file is

[JSX Cheatsheet for Section 2](https://jsx-notes.vercel.app/#Returning%20JSX)

# Building with reusable components

## Prop system

1. Pass data from parent component to child component
2. Allows a parent to configure each child differently
3. ONE WAY FLOW

## Destructing

Example `const {title, handle} = props; ` OR more likely `ProfileCard({title, handle})`

- Create variables for all props values
- Good since you do not always need all values from props

## Adding images

- If image is less than 9.7 kb, served as base64 encoded
- If image is greater than 9.7 kb served as seperate file
- Add attribute `alt="name of image"` to get rid of error for screen reader

# State: How to change your app

## Using events steps

- "I'd like to run some code when a user does something"
- Events can be listened for by adding prop to component, like ` <button onClick={handleClick}/>`

1. Decide what event you'd like to watch for
2. Create a function, called usually a handler or a callback. Function called by another piece of code
3. Name the function using pattern of handle + EventName. Example `handleClick`, `handleScroll`, `handleMouseUp`, `onClick`, `handleButtonClick`
4. Pass function as a prop to a plain element. Example
   `button onClick={handleClick} />`
5. Make sure you pass using valid event name to child
6. Make sure pass event in as reference. Example `handleClick` NOT `handleClick()`

## What is State?

- "I'd like to change something on the screen"
- Data that change as the user interacts with out app
- When this data changes, React will update content on the screen
- This is the one-and-only way we change content

## Using state in app

1. Assign state a top of component function with useState function
2. Give a value to the useState function. This is the DEFAULT value.
3. Use the state in some way in our component. Use setter function.
4. When user does something, update the piece of state. Causes "rerender".

## What is an Array Destructuring?

- useState returns a variable and method to change variable (setting function)
