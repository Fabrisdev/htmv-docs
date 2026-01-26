---
sidebar_position: 9
---

# Your first API
Okay! Now that we learned all this, let's apply it in our project.
We could make a new route file inside `/api/tasks` for it, but since this project's only entity are tasks we might aswell just stick to working in our current file.
If you wish to split it into another route file then go ahead! Just remember to change the URL once we start trying out our API.

## How we're gonna tackle this
For now, we'll simply store our tasks on RAM inside a variable. Later on, we'll see how we can connect our app with a DB instead.

```ts
import { view } from 'htmv'
 
type Task = {
  title: string
  description: string
  done: boolean
}

const tasks: Task[] = [] // No tasks by default

export default () => {
  return view('list', { tasks })
}

export function POST() {
  tasks.push({
    title: "My task",
    description: "The description",
    done: false
  })
}
```

I've simply moved our tasks variable out of the default function export so that we can access it globally. Finally, I've created a new POST method for our route which for now just creates a new task with some hard-coded attributes.