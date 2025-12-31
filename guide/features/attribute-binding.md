---
sidebar_position: 7
---

# Attribute binding
Although being able to interpolate values is nice, sometimes you need *just a bit* more than that.

For example, let's say you have a task you wish to show if it's done or not:

The first step would be to pass the `{task.done}` value to the view.

After that, you should have an `<input type="checkbox">` element inside your view.

Next to that, one would think *"I'll just add a `checked={task.done}` attribute to it!"*

Like so: `<input type="checkbox" checked={task.done}>`

However, on opening your web page you'll realize the input is always checked. No matter whether `task.done` is truthy or not. This is because for attributes like `checked`, HTML doesn't care if the value for the attribute is truthy or not. It only checks if the attribute is present or not. Therefore, it is impossible to solve this with simple interpolation.

For this, you'll need attribute binding. And HTMV has got your back! Simply add a `:` before the attribute. That's it!

`<input type="checkbox" :checked={task.done}>`

This tells HTMV's compiler: *"Don't add the attribute AND value, just add the attribute alone IF the value is truthy!"* 