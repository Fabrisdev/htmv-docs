---
sidebar_position: 5
---

# Your first view
As previously stated, all views/components are stored inside your `views` folder.
By default, HTMV comes with a built-in `example` view. For now, let's delete in order to start from scratch.

After that, you should be left with an empty `views` folder. Inside it, let's create your first view. We'll call it `list.html`.
:::danger
As you may have noted, we're using the `.html` extension for views. However, that is subject to change in the future once the `.htmv` extension is available. For more information, check out the [linting article](/docs/features/linting).
:::

## The code
Inside your view, you can write any HTML! No need to learn a new language.
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>TODO CRUD</title>
  </head>

  <body>
    <h1>Welcome!</h1>
    <p>Here is where available tasks will appear.</p>
  </body>
</html>
```
As you can see, working with views feels just like working with vanilla HTML. However, views do in fact add some new features, which we'll discuss later.

## Okay, but how do I see it now?
We don't have a way to see our webpage just yet. This is because we haven't yet told our router to render our `list` view whenever a user visits our page.  
In the next section, we'll be doing just that!