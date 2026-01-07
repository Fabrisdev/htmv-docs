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