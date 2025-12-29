---
sidebar_position: 4
---

# Renaming folders
If you wish to rename either the `views`, `routes` or `public` folders you can do so in `index.ts` as follows:
```ts
setup({
	routes: path.join(dirPath, "my_custom_routes_folder"), 
	views: path.join(dirPath, "stuff", "views"),
	public: path.join(dirPath, "static"),
	port: 3000,
});
```
Just change the string for the new name you wish for. Note that when doing so `htmv gen` will now need `--path` flag passed to know where to find them.