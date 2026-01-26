---
sidebar_position: 8
---

# Your first API
Good job keeping up so far! Next up in our list is being able to create and delete tasks, and for that we'll be making our first API!

## An example
Making an API is just like making any other route. For example, let's say we wish to have an endpoint for retrieving the users from your DB. You would do so like this:
```ts
export async function GET() {
  const users = await fetchUsers() // replace this with however it is done on your DB
  return users
}
```
We could also have a `POST` method to add new users onto the DB.
```ts
import type { RouteParams } from 'htmv'

export async function POST(params: RouteParams) {
  const { username, email } = params.query;
  await addUser({ username, email }) // replace this with however it is done on your DB
  return ""
}
```
And since we don't actually wish to return a body, just a 200 OK response we might aswell use the built-in `ok()` response helper.
```ts
import type { RouteParams } from 'htmv'
import { ok } from 'htmv/http'

export async function POST(params: RouteParams) {
  const { username, email } = params.query;
  await addUser({ username, email }) // replace this with however it is done on your DB
  return ok()
}
```

## Error handling
But what if something goes wrong? For example, if the username is less than our required 6 letters long? We can simply do the following:
```ts
import type { RouteParams } from 'htmv'
import { ok, badRequest } from 'htmv/http'

export async function POST(params: RouteParams) {
  const { username, email } = params.query;
  if(typeof username === "string" && username.length >= 6) {
    await addUser({ username, email }) // replace this with however it is done on your DB
    return ok()
  }
  return badRequest("Username is either not present or is less than 6 characters long") // returns a 400 BAD REQUEST response
}
```
Of course, you're also missing checking for the email, but I'll leave that as your homework.

Finally, if you need your API to appear after `localhost:3000/api`, remember to create a folder named `api` inside the `routes` folder and work your way from there.

## Back to our project
Okay! Now that we learned all this, let's apply it in our project.
We could make a new route file inside `/api/tasks` for it, but since this project's only entity are tasks we might aswell just stick to working in our current file.
If you wish to split it into another route file then go ahead! Just remember to change the URL once we start trying out our API.

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