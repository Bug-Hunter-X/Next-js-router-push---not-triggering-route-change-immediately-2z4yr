# Next.js router.push() Event Timing Issue

This repository demonstrates a common issue in Next.js applications where the route change event doesn't fire immediately after calling `router.push()`. This can lead to unexpected behavior if you rely on the route change to update the component's state or perform other actions.

## Problem

The provided code snippet attempts to navigate to '/another-page' using `router.push()`.  The `console.log` statement after `router.push()` is expected to execute *after* the page is navigated. However, due to the asynchronous nature of `router.push()`, `console.log` may execute before the actual route change completes, leading to incorrect behavior.

## Solution

The solution involves using `router.events` to listen for the `routeChangeComplete` event, ensuring that the code dependent on the route change only executes after the navigation is fully finished. 

## Usage

1. Clone the repository
2. Navigate to the directory
3. Run `npm install`
4. Run `npm run dev`
5. Observe the behavior in the browser. 