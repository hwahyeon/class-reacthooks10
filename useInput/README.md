# useInput Custom Hook
The `useInput` custom hook simplifies handling user input in React applications. It enables easy input value management and validation, providing a straightforward way to update and validate input fields.


## Usage
The `useInput` hook is designed to be versatile, supporting various use cases through the optional `validator` function. Here are a few examples demonstrating how to use it:


### Example 1: Exclude Specific Characters
To prevent users from entering an "@" symbol in the input field:
```js
import useInput from "/use-input"

const App = () => {
  const validator = value => !value.includes("@");
  const name = useInput("Mr. ", validator);
  return (
    <div className="App">
      <h1>Hello</h1>
      <input placeholder="Name" {...name.props} />
    </div>
  );
};
```
### Example 2: Limit Input Length
To limit the input value length to 15 characters:
```js
import useInput from "/use-input"

const App = () => {
  const validator = value => value.length <= 15;
  const name = useInput("Mr. ", validator);
  return (
    <div className="App">
      <h1>Hello</h1>
      <input placeholder="Name" {...name.props} />
    </div>
  );
};
```

## How It Works
- **initialValue**: Sets the initial value of the input field.
- **validator**: An optional function that determines whether the input value should be updated based on custom logic. It should return `true` for valid inputs and `false` for invalid inputs.