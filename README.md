# React setInterval Memory Leak

This repository demonstrates a common memory leak in React components that use `setInterval` within the `useEffect` hook without proper cleanup.

## Bug Description

The `MyComponent` uses `setInterval` to update a counter every second. However, it fails to include a cleanup function in the `useEffect` hook to clear the interval when the component unmounts. This results in the interval continuing to run even after the component is no longer rendered, leading to a memory leak.

## How to reproduce

1. Clone the repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the counter increasing even after navigating away from the component or refreshing the page.

## Solution

The solution involves adding a cleanup function to the `useEffect` hook that calls `clearInterval` to stop the interval before the component is unmounted.

## License

MIT