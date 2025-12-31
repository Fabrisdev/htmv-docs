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