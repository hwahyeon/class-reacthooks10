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
import useTabs from "/use-tabs"

// Sample component using the useTabs hook
const App = () => {
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

export default App;
```

## Arguments
- **initialTab** (Number): The index of the initial active tab.
- **allTabs** (Array): An array of objects, with each object representing a tab. Each object should include:
  - **tab** (String): The label of the tab.
  - **content**: The content displayed when the tab is active.
Ensure `allTabs` is a non-empty array for the hook to function correctly.