# Programming Languages

## Javascript

Because JavaScript is single-threaded, but thanks to the event loop, it feels asynchronous and fast.
You can: fetch data, wait for user input, do animations…without freezing your app.

Event Loop Summary
・JavaScript runs one thing at a time using a call stack.
・Async tasks like setTimeout or fetch are handled by Web APIs in the browser.
・When they're done, their callbacks go into a callback queue.
・The event loop keeps checking:
・“Is the call stack empty? If yes, run the next thing in the queue.”