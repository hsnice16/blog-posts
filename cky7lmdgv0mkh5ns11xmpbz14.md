## Why you should not use export default in JavaScript?

Many of us think when we have only one thing to export from a file we should use `export default` and if there is more than one thing then use named `export` alone or use it with `export default`.

And it is totally fine to use `export default` for small projects, **But** if you are working on a large project **Or** working on a project with a team then using `export default` might not be a good choice.

Let us understand, Why?

## ❓ Why we should not use export default

The first reason for not using `export default` is that While using `import` we can change the name of the exported thing. Or to say, we have the option to choose a name for default exports

Like, if we have a default export like this

```jsx
// helloWorld.js

export default function helloWorld() {
		console.log("Hello! World");
}
```

So, at the time of `import`, we can use any name

```jsx
import HelloWorld from "helloWorld.js";
import HWorld from "helloWorld.js";
```

Both are correct. And both will import the `HelloWorld()` function.

So, if we are working with a team changing names may cause a lot of problems with the debugging of the code or with the refactoring.

But to overcome this, and to keep code consistent, there is a rule that the name of the imported thing should match with the importing file name. Like this

```jsx
import GetItem from "getItem.js";
import FindUser from "findUser.js";
```

But still, there is a problem with default exports.

### default export makes re-exporting a little bit trickier

If you do not know **What is a re-export?** then, when we `import` a thing but instead of using it we directly `export` it, Like this

```jsx

// first
import HelloWorld from "helloWorld.js";
export { HelloWorld };

// second
import {getUser, findUser} from "user.js"; // named export
export {getUser, findUser};
```

Here, in the first, we are importing `HelloWorld` and then at the next line, we are exporting it. We have a short syntax to do the same thing when we want to `import` and `export` at the same time then we can use `export ... from` to do that, Like this

```jsx
export {default as HelloWorld} from "helloWorld.js";
export {getUser, findUser} from "user.js";
```

**Things to note**

- To re-export a default export, we have to use `export {default as HelloWorld}`. We can not use `export HelloWorld from “helloWorld.js”`, this will result in a `Syntax Error`.
- If our file contains many named exports and one default export, then we can do something like this
    
    ```jsx
    export * from "items.js"; // to import and export all named exports 
    export {default} from "item.js"; // to import and export default export
    ```
    
    Since we are doing a special thing only for a default export, that’s why many developers do not like to use `export default`.
    
For these reasons, we should not use export default.

---

## 🏁 That’s It for this

Hoping this blog will help you. And you will also start to look at places where you should use `export default` and where you should not. 

Comment below, How was this blog? or any feedback. I would love to read your comments.

Connect with me on [Twitter](https://twitter.com/hsnice16)