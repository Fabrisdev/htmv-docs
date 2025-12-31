---
sidebar_position: 6
---

# Interpolation
As mentioned briefly at the start of the docs. One of HTMV's main features is interpolation.

What's that? Put simply, have a value on the backend you wish to show when rendering the view? Just use interpolation!

Here's a simple example which lets you randomly show different strings on page load:
```ts
// index.ts route
import { view } from 'htmv'

export default () => {
	const messages = ["Welcome back!", "How was your day?", "We're glad you're back."]

	return view('example', {
		message: getRandomValue(messages) // the message variable will get sent to the view for you to use freely.
	})
}

function getRandomValue(arr: Array) {
	return arr[Math.floor(Math.random() * arr.length)]
}
```
```html
<!-- example.html view -->
<p>{message}</p> <!-- here we are accessing the message variable -->
```