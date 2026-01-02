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