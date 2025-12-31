---
sidebar_position: 4
---

# Understanding the project structure
Before coding, let's take a moment to familiarize ourselves with HTMV's default project structure.

![Image of a default project structure](/img/project-structure.png)


:::note Irrelevant items
These are items you usually don’t need to interact with.
- `node_modules`  
  Contains project dependencies installed by the package manager.  
  You should not edit files here manually.
:::

:::tip Important items
These are items you might find useful.
- `public`  
  Any files put here will be served at `/public/`. This is useful for static files such as images, javascript code, CSS styles, and others.
- `routes`  
  All your routes will be defined inside here. We'll go over this later on this tutorial.
- `views`  
  All your views/components will be defined inside here. We'll go over this later on this tutorial.
:::