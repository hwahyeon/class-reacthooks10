# useTitle Custom Hook
The `useTitle` custom hook enables dynamic updates to the document's title, making it easy to reflect the current state or page within a React application.

## Usage
Here's how to use the `useTitle` custom hook within your React component:



The hook returns a function that you can use to update the title.
```js
import useTitle from "/use-title"

const App = () => {
  const titleUpdate = useTitle("Loading...");

  // Update the title after 5 seconds
  setTimeout(() => titleUpdate("Home"), 5000);

  return <div></div>;
};
```

## Arguments
The `useTitle` hook accepts a single argument:
- **initialTitle** (String): The initial value you want to set for the document's title when the component mounts.