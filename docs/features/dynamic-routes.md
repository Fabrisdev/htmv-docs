---
sidebar_position: 2
---

# Dynamic routes
Sometimes you don't know the exact route (this is more common in `APIs`). For example, let's say you want to have a route `/api/user/USER_ID_HERE`. Of course you don't want to have a million folders every single one named with a different user id. That's where dynamic routes come into play.

Let's setup one. Just rename your file to `/api/user/:id`.

That's it! Now you can access it inside your route like this:
```ts
import { type RouteParams } from "htmv";

export default function UserEndpoint(routeParams: RouteParams) {
	const { id } = routeParams.params
	return `Hello user ${id}!`
}
```
Now when you go to `/api/user/1000` you should see `Hello user 1000!`.