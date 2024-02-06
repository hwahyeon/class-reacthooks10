# useTabs Custom Hook
The `useTabs` custom hook is designed to facilitate tab management in React applications. It provides a simple way to switch between different content sections based on tab selection.


## Usage
To use the `useTabs` hook in your project, follow these steps:

### Step 1: Define the Tabs Content
Create an array of objects where each object represents a tab with its respective content.
```js
const content = [
  {
    tab: "Section 1",
    content: "I'm the content of the Section 1",
  },
  {
    tab: "Section 2",
    content: "I'm the content of the Section 2",
  },
];
```

### Step 2: Implement `useTabs`
Import and use the `useTabs` hook within your component to manage the tabs.

```js
import React from 'react';
import { useState } from "react";

// Define the useTabs hook here or import it if it's defined in another file
const useTabs = (initialTab, allTabs) => {
  const [currentIndex, setCurrentIndex] = useState(initialTab);
  
  if (!allTabs || !Array.isArray(allTabs)) {
    return;
  }
  
  return {
    currentItem: allTabs[currentIndex],
    changeItem: setCurrentIndex
  };
};

// Sample component using the useTabs hook
const page = () => {
  const { currentItem, changeItem } = useTabs(0, content);
  
  return (
    <div>
      {content.map((section, index) => (
        <button onClick={() => changeItem(index)}>{section.tab}</button>
      ))}
      <div>{currentItem.content}</div>
    </div>
  );
};

export default page;
```

## How It Works
- **Initialization**: The `useTabs` hook takes two arguments: the index of the initial tab (initialTab) and an array of tab objects (allTabs).
- **State Management**: It uses the useState hook to keep track of the current active tab index.
- **Flexibility**: The hook checks if the allTabs array is valid and returns the current item's content and a function to change the active tab.
- **Rendering**: In your component, map through the content array to render tab buttons. Use the changeItem function to update the current tab on click.