---
sidebar_position: 5
---

# Code generation
Do you often forget how to write boilerplate code? Why not just let HTMV do it for you?
As you know, HTMV comes with the CLI tool you used when creating the project. But it also has the command `htmv gen` which allows you to generate a basic template for a view or route.

The syntax is as follows:
```bash
bunx htmv@latest gen {TYPE} {NAME} {OPTIONS}
```
For example, to create a view called MyCoolView:
```bash
bunx htmv@latest gen view MyCoolView
```
Running this will generate a view in the `views` directory of your project. The other remaining type is `route` which works the same way but creates the route in your `routes` directory.

However, note that if you have changed the name of your folders HTMV will be unable to find them and you'll have to manually specify the folder you wish for the generated file to be placed in as follows:
```bash
bunx htmv@latest gen view MyCoolView --path cool_stuff/my_custom_views_folder
```