---
sidebar_position: 8
---

# Your first API
Good job keeping up so far! Next up in our list is being able to create and delete tasks, and for that we'll be making our first API!

Making an API is just like what we just did. For example, let's say we wish to have an endpoint for retrieving the users from your DB. You would do so like this:
```ts
export async function GET() {
  const users = await fetchUsers() // replace this with however it is done on your DB
  return users
}
```