## Absolute path in react js

Why this blog? recently I tweeted a tweet in which I said to use absolute path with import statement in react. And on that tweet, many folks commented what was I meant by saying that. So, instead of explaining each one personally, I thought I should write a blog on that. So that’s why I am writing this blog.

> You can check the tweet [here](https://twitter.com/hsnice16/status/1505435737654669312?s=20&t=5_IgeaxdZzeAnoDxbamEkg).
> 

Nowadays, I am working on an e-commerce personal project. And in that, a reviewer, while reviewing my PR, suggested to me to use absolute path rather than relative in react.

So, I searched for that and found that it is really nice. It prevents the deep backward drilling of relative paths. And also make code more readable. So, I would explain how I implemented that in my project step by step.

---

## Step 1

First, let us see what do we mean by the absolute path and relative path?

So, suppose we have the following folder structure in our project

```jsx
src/
|
|- components/
|      |- heading/ 
|      |    |- Heading.jsx
|      |- index.js
|
|- pages/
      |- home/
          |- Home.jsx      
```

Now, in `Home.jsx` we want to use the `Heading.jsx` component.

So, how can we use that? We can use it by importing it into our `Home.jsx` file. 

1. One way to import it is by using a **relative path**, Something like this

```jsx
// in Home.jsx
import { Heading } from "../../components";
```

Here, you may ask that we are not importing it directly from the `Heading.jsx` file itself. So, as you can see we have created a file named `index.js` in the `components`. 
So, we will re-export it from there. And then we can use it like this (as shown in the above code block).

2. Another way, in which we can import `Heading.jsx` is by using the **absolute path**, by that my mean is

```jsx
// in Home.jsx
import { Heading } from "src/components";
```

Only by doing this, we can see how much the readability of the code has increased. If you say, what does it make difference?

So, suppose the nesting is 4 or 5 level and there are different folders from which we are importing things, then using **relative path** will have a high impact on the readability and on code cleanliness. 

## Step 2

Is that only you want to discuss? No, not only this.
In react we can improve the absolute path a bit more. For that, we have to create a `jsconfig.json` file at the root level of our project directory (it would be close to your `package.json` file)

In `jsconfig.json` file, write the following lines 

```jsx
{
  "compilerOptions": {
    "baseUrl": "src"
  },
  "include": ["src"]
}
```

And now, in `Home.jsx` we can impore the `Heading.jsx` like this

```jsx
// in Home.jsx
import { Heading } from "components";
```

That’s it. And this will import the following components.

When you will have many components, and you want to use them in a deeply nested file, then using an absolute path can be very useful in terms of readability and code cleanliness.

And, you can use this for other things too. Like for reducers, utils, and for other files.

## Step 3

If your server is already running, and you have done all these changes in your directory. Then your app will crash and you will have errors like `file directory is not found`. Something like this,

What should I do then?
So, it’s very easy. Just stop your server, and start it again. And now everything will work as it was before.

---

## 🏁 That’s it

Thanks for reading it till the end. I would love to read your feedback on this blog in the comments below.

*You can connect with me on [Twitter](https://twitter.com/hsnice16)*

## References

- [Create React App](https://create-react-app.dev/docs/importing-a-component#absolute-imports)
- [Medium Blog](https://saurabhshah23.medium.com/react-app-with-absolute-paths-using-jsconfig-json-2b07b1cb24d4)