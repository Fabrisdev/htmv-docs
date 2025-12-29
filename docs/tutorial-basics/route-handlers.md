---
sidebar_position: 3
---

# Route handlers
Following with `APIs`, you sometimes want a single endpoint for your users, for example `/api/user` and depending on the method used on the request act accordingly. For example, create an user with method `POST`, get users with method `GET` and more. 

Normally you'd do that programatically like the following:
```ts
import { type RouteParams } from "htmv";

export default function UserEndpoint(routeParams: RouteParams) {
	const method = routeParams.request.method
	if(method === "GET") {
		// list users
	}
	if(method === "POST") {
		// create user
	}
}
```
Route handlers allow you to this in an easier way. Just have functions for each method!
```ts
import { type RouteParams } from "htmv";

export function GET(routeParams: RouteParams) {
	// list users
}

export function POST(routeParams: RouteParams) {
	// create user
}
```
Note how the `default` keyword was removed, that keyword is instead reserved for when you want to hit all endpoints (`ALL` method).

Supported methods currently are:
- GET
- POST
- PUT
- PATCH
- DELETE
- ALL (add `default` keyword)