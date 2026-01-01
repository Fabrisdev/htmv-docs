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

