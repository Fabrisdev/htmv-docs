---
sidebar_position: 3
---

# Installation
Our first step towards building our TODO app is installing HTMV. But before that, a quick warning:

:::danger[Precautions]

HTMV currently only works on Bun. Routing on Node.js is broken. Please take note and only use Bun with it while I'm working on Node.js support.

:::

## Creating a project
It's simple! Just use htmv's [CLI](/docs/getting-started/what-is-htmv)!
```bash
bunx htmv@latest new my_todo_app
```
This will create an htmv project on the folder `my_todo_app`. Dependencies are already installed! No need for a `bun install`.

Finally, open up `my_todo_app` on your editor of choice. We're ready to begin building!

## Plus: Using HTMV's vscode extension
If you wish for syntax highlighting inside your `.htmv` files, you can install HTMV's Visual Studio Code extension. The extension also provides some code snippets for working with HTMV's special elements.

You can get it [on the Marketplace](https://marketplace.visualstudio.com/items?itemName=fabrisdev.htmv).

## Running the server
Let's check our app is working. You can start the server with `bun dev`. After that, you should now be able to see your page in `http://localhost:3000`!

## Final note
Did you see how the `{title}` value on our view changed to the one we gave it on our route? Now that's where HTMV gets fun! Just as we now did you could also do more complex stuff like access your DB's data and show it in a nicely form.