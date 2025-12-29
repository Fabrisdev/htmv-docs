---
sidebar_position: 1
---

# Installation

:::danger[Precautions]

HTMV currently only works on Bun. Routing on Node.js is broken. Please take note and only use Bun with it while I'm working on Node.js support.

:::

# Getting started
It's simple! Just use htmv's CLI!
```bash
bunx htmv@latest new my_cool_project
```
This will create an htmv project on the folder `my_cool_project`. Finally `cd` into it to get started. Dependencies are already installed. No need for a `bun install`.

## And that's it! We're done. 
Now let's try it! You can simply start it with `bun dev`. After that, you should now be able to see your page in `http://localhost:3000`.

## Final note
Did you see how the `{title}` value on our view changed to the one we gave it on our route? Now that's where HTMV gets fun! Just as we now did you could also do more complex stuff like access your DB's data and show it in a nicely form.