---
sidebar_position: 1
---

# What is HTMV?

HTMV is a web framework for server-side rendering. It features an HTML-like templating system which lets you
easily build fast and safe applications through explicit data flow. You know all the data passed, no hidden secrets.
Opposite to many other web frameworks, no code evaluation is allowed which leads to safer and more predictable rendering.

## Features:
- 0 javascript sent by default to the client.
- File system based routing.
- Simplicity.

## When/For what should I use it?
First things first, it isn't for everyone.
So let's start with some quick questions first.
1. Your site needs reactivity? -> **HTMV is not for you**
2. Do you need an SPA-like experience with client-side routing? -> **HTMV is *most likely* not for you** *(altought you can get it to work)*
3. Do you want full control over every file sent to the user? -> **HTMV is a good fit**
4. Is most of your UI renderable in the server? -> **HTMV is a good fit**
5. Do you value simplicity, safety, and predictability over abstraction? -> **HTMV is a good fit**