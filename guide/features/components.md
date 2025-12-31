---
sidebar_position: 8
---

# Components
One of HTMV's key values is that a component is just a view. Therefore, your `example` view is already a component!

However, for HTMV to be able to differentiate it from an HTML element it must start with an uppercase (`Example`).

Let's create a header component with `bunx htmv gen view Header`

Inside we can make use of attributes like so:
```html
<h1>{title}</h1>
<h2>{description}</h2>
```
Lastly, in our `example` view, let's call it!
```html
<Header title="My cool webpage" description="It's purpose is to test HTMV's components!"/>
```

That's it. We can also make use of the `children` prop, like so:
```html
<!-- example view -->
<Header description="It's purpose is to test HTMV's components!">My cool webpage</Header>
```
```html
<!-- Header view -->
<h1>{children}</h1>
<h2>{description}</h2>
```