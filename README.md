# React history state

React History State is an extension of React's built-in `useState` hook. As the name suggests, it helps manage state history in React, allowing you to easily undo and redo state changes



## Features

- Simple state management with useState-like API
- Undo and redo functionality
- Clear history support
- TypeScript support with full type safety
- Options for throttling, debouncing, and time-based or count-based commits


## Installation
Install using npm:

```bash

npm install react-history-state

```



## Usage example

```js

import { useHistoryState } from 'react-history-state'

export default function App() {
  const [text, setText, undo, redo, clear] = useHistoryState('');

  return (
    <>
      <input
        type="text"
        value={text}
        onChange={(e) => setText(e.target.value)}
      />
      <button onClick={undo}>Undo</button>
      <button onClick={redo}>Redo</button>
      <button onClick={clear}>Clear</button>
    </>
  )
}

```


## Typescript

```js

const [count, setCount, undo, redo] = useHistoryState<number>(0);

setCount(1) // Works

setCount('2') // Type error

```



## Options

```js

// throttle
  const [state, setState, undo, redo] = useHistoryState('', {
    throttle: 500 // Updates history at most every 500 milliseconds
  });

  // debounce
  const [state, setState, undo, redo] = useHistoryState('', {
    debounce: 500 // Updates history 500 milliseconds after inactivity
  });

// commitEvery
  const [state, setState, undo, redo] = useHistoryState('', {
    commitEvery: 5 // Updates the history once every 5 state changes
  });

```

## License

MIT
