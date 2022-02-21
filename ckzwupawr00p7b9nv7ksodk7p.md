## Why do we call ReactJs declarative?

If you have coded in ReactJs, or if you are coding in it. Then you must have heard of these two terms, Declarative and Imperative.

Even, on the official site of [ReactJs](https://reactjs.org/), it is mentioned that one of its usefulness is Declarative (others are Component-Based and Learn Once, Write Anywhere**)**. 

But why do we call it declarative and not imperative? So with that question let’s start our blog.

Hey! 👋 everyone, my name is Himanshu Singh. Currently, I am in college and nowadays I am learning web development in [neogCamp](https://neog.camp/).

In this blog, We will get to know why ReactJs is a declarative way of programming.

---

### ❓Imperative and Declarative

First lets we discuss, what is an imperative way of programming and a declarative way of programming?

In the ***Imperative*** way of programming, we write each step that will lead us to the desired result. Like, suppose we want to find the sum of all the elements of an Array. So, to do that we will do something like the below code, in Javascript

```jsx
const sumOfArrayElements = (array) => {
	let sum = 0;
	
	for (let element of array) {
		sum += element;
	}
	
	return sum;
}
```

Here, we can see that we have explicitly written each step that will be required to get the sum. 

Steps are:

- Initialize the variable that will store the sum
- Iterate over the array and add each element present in the array to the *sum* variable
- return the sum

Now, before discussing how we can improve this? let's discuss how we will do this in a ***Declarative*** way of programming?

So, in JavaScript, we can do something like this

```jsx
// const array = [1, 2, 3];

array.reduce((sum, element) => sum + element, 0);
```

That’s it. One line code and we will get the sum of all the elements.

**Did you see it?** declarative program abstracts out the code. Now we are only saying ***What we want,*** for each element of the array run the reducer function ((sum, element ) ⇒ sum + element), where the initial value of the sum is 0. 

While at the time of imperative, we were saying ***How the Javascript can find the result we want,*** by writing each step explicitly.

### ❓So, How Reactjs is declarative

Now, let’s see how reactjs is declarative? If you have worked with reactjs before then you may have taken a user input in your app, and on change of the input you were storing the entered value and then were showing that to the user (*controlled input*).

The code for the above will look something like below-

```jsx
export const App = () => {
	const [username, setUsername] = useState("");

	const handleUsernameOnChange = (event) => {
		setUsername(event.target.value);
	}

	return (
		<div>
			<input 
				onChange={handleUsernameOnChange} 
				type="text" 
        name="username" 
				value={username} />
		</div>		
	);
}
```

 

Now, here there are two things to notice.

1. we are just saying that `onChange` of the input, call `handleUsernameOnChange()` with `event` as the argument.
2. Whatever the `username` has value, show it in the `input`.  

**But, what is declarative here?**

Now, suppose if the same thing we wanted to achieve in the Vanilla JS, then how we had done?

1. Get the reference of the `input` on which we want the event.
2. Add an event listener on that `input`, and give a callback to the event listener.
3. In the callback, get the value the user entered. And store it, for future use, at some other place.

So, In react, we said ***what we want,*** we don’t care how the react will call the function on every change and will show the new value. While in Vanilla JS, we said ***how the things should be done,*** means first get the input element, then add an event listener, and then in the callback, get the input value and store it for future use.

> Declarative programming abstracts out the things.
> 

---

### 🏁 That’s all

Thank you for reading it till the end. Do let me know, in the comments, how was the blog or any feedback you like.

You can connect with me on [Twitter](https://twitter.com/hsnice16), I am quite active there.