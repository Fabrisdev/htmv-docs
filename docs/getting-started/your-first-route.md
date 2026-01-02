---
sidebar_position: 6
---

# Your first route

In the previous section, we prepared our view for rendering. Now it's time to tell the router we wish to send it to the user when they visit the page.  
  
For that, let's head over to our `routes` folder. There should already be an `index.ts` file inside there. Just as we did for our views, let's delete it in order to start from scratch.

## How routing works in HTMV
HTMV makes use of file system based routing. If you've used a framework like Next.js before, this will be very similar to it.  
A route in HTMV is simply an `index.ts` file inside the routes directory.
The file path determines the URL, and the exported functions determine how that route behaves.

## An example
Let's say we would like to show our cool view we just made in `localhost:3000/blog/welcome/`
For that, we'd have to first create a `blog` folder and inside it create a `welcome` folder. Finally, for HTMV to actually register it as a route we must create an `index.ts` file inside it.

## Route handlers
That's good and all, but how do I tell it which view to render when the user visits that route?

Good question. For that, we make use of route handlers. For example, if we wish to send it whenever a `GET` request is made on that route we can do so like this inside our just created `index.ts`:
```ts
import { view } from 'htmv'
 
export function GET() {
  return view('list') // list is the name of the view we had just created. Make sure not to include the .html extension
}
```
Simple, right? We simply must have an exported function called `GET` and inside it we return whatever we wish to render when the user visits that page. In this case, we make use of the `view` function to render our view, but we could also have just rendered plain text by just returning a string.

`GET` however, is not the only available method to use. Another common one is `ALL`, which simply means it doesn't matter what method the user uses when making the request. HTMV considers it the default method and so you must use the `default` keyword when working with it:
```ts
import { view } from 'htmv'
 
export default function MyRoute() {
  return view('list')
}
```

Note how the name of the function is no longer of importance. And so we may as well just use an arrow function:
```ts
import { view } from 'htmv'
 
export default () => {
  return view('list')
}
```