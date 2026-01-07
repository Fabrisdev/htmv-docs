---
sidebar_position: 7
---

# What's next?
If you got here, good job! That means you should already have seen your webpage working.  
Next up in the list would be rendering something more than just a simple hello world.

## Creating some tasks
Let's start by creating some tasks for us to render later.
Let's go over to our newely created `routes/index.ts` and change it a little:
```ts
import { view } from 'htmv'
 
type Task = {
  title: string
  description: string
  done: boolean
}

export default () => {
  const tasks: Task[] = [
    {
      title: "Clean the room",
      description: "Perhaps I should clean my room...",
      done: false
    },
    {
      title: "Take out the dog",
      description: "I should take the dog to the park later",
      done: false
    }
  ]
  return view('list', { tasks })
}
```

## The view function
`view` accepts up to two parameters. The first one is required and is the view's name we wish to render. The second however, is optional and is an object with the props that will be sent to the view before rendering.

In resume, I've simply created an object containing some hard-coded tasks and appended them to the view as props.

## But how do I see them?
If you go back to your webpage, you'll see nothing has changed. That is because we are not yet making use of the `tasks` prop.
Let's update our view in order to do so:
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>TODO CRUD</title>
  </head>

  <body>
    <h1>Welcome!</h1>
    <p>Here is where available tasks will appear.</p>
    <p>These are the tasks: {tasks}</p>
  </body>
</html>
```
I've simply added an extra paragraph at the end where im using HTMV's special syntax `{}` in order to tell it we wish to render the tasks there.

However, if you refresh and visit it right now you'll get something like: `[object Object]`. That is because, when rendering, HTMV tries to convert whatever type our prop is into a string in order to be able to render it as plain HTML. However, since that prop is of type object it fails and produces that output.

In order to correctly render it we should instead render each field of our tasks separately. We could try something like
```html
<p>The title is: {tasks.title}, the description is: {tasks.description}</p>
```
But since our `tasks` prop is also an Array that also won't work. Instead, we can make use of HTMV's `For` element which lets you loop through each of an array's elements:
```html
<For task in tasks>
  <p>Title: {task.title}</p>  
  <p>Description: {task.description}</p>  
</For>
```
Yes! This last one does work. However, we could make it a bit easier to read by making use of an ordered or unordered list:
```html
<ol>
  <For task in tasks>
    <li>
      <h2>Title: {task.title}</h2>  
      <p>Description: {task.description}</p>  
    </li>
  </For>
</ol>
```
## Attribute binding
Note however how we're still not using our `{task.done}` prop. This was done intentionally since rendering this prop will be a bit different since it's a boolean instead of a string.

We could do just as we did and simply add a third line inside our `<li>` containing
```html
<p>Is it done? {task.done}</p>
```
However, it would be nicer having something that can either be toggled ON or OFF depending on whether our prop is truthy or falsy. Since right now it would simply render as
```html
<p>Is it done? true</p> <!-- Or false -->
```
For example, a checkbox would fit this perfectly! (`<input type="checkbox">`)  
We could `bind` our `task.done` prop to its `checked` attribute! However, when we go do so...
```html
<input type="checkbox" checked="{task.done}">
```
We realize our webpage marks every task as checked no matter whether it actually is done or not.  
This is simply due to how HTML behaves. It does not check for the attribute's value and simply checks whether or not the attribute is set or not. 

This is where HTMV has to step in in order to make it work. HTMV's views add a new special syntax for adding an attribute to an element ONLY IF thy prop assigned to it is truthy.  
And in order to use it, you simply have to add a `:` to the start of it.
```html
<input type="checkbox" :checked={task.done}>
```
However, note that in order to use the special syntax it is needed to remove the double quotes.

## Final code
Sorry for the long rant! In the end, your view should be looking like this:
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>TODO CRUD</title>
  </head>

  <body>
    <ol>
      <For task in tasks>
        <li>
          <h2>Title: {task.title}</h2>  
          <p>Description: {task.description}</p>  
          <input type="checkbox" :checked={task.done}>
        </li>
      </For>
    </ol>
  </body>
</html>
```
And your route like this:
```ts
import { view } from 'htmv'
 
type Task = {
  title: string
  description: string
  done: boolean
}

export default () => {
  const tasks: Task[] = [
    {
      title: "Clean the room",
      description: "Perhaps I should clean my room...",
      done: false
    },
    {
      title: "Take out the dog",
      description: "I should take the dog to the park later",
      done: false
    }
  ]
  return view('list', { tasks })
}
```
If that's what it looks like and it's working then you can go ahead onto the next chapter!  
Remember if you're having trouble keeping up you can also check out the entire code on GitHub.