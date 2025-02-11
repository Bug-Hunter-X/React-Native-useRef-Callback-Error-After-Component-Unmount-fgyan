# React Native useRef Callback Error After Component Unmount

This repository demonstrates a common error in React Native when using the `useRef` hook with asynchronous operations. The problem occurs when a component is unmounted before the asynchronous operation within the `useRef` callback completes, leading to errors or unexpected behavior. The solution uses the cleanup function provided by `useEffect` to properly handle the callback and prevent these errors.

## Bug Description

The bug arises because the callback function within `useEffect` continues to execute even after the component is unmounted. This results in errors when accessing `myRef.current` because the component no longer exists in the DOM.

## Solution

The solution employs the cleanup function of the `useEffect` hook. This function is executed before the component is unmounted, providing an opportunity to clean up resources, cancel timers, or gracefully handle the callback, thus preventing the errors.