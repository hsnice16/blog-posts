## Working with DOM in JavaScript

Hi everyone! I'm Himanshu, a Front-end web developer. Being a Front-end developer, I know that having knowledge of DOM is important, so in this blog, I will cover those parts of DOM which will give you a working knowledge about them.

In this blog, you will see 

- What's a DOM?
- Tree Data Structure
- Traversing the DOM tree
- Changing the Document

let's begin!

## What's a DOM?

Whenever you open an HTML file in your browser, the browser parses the file and builds up a model of the document structure, and then uses this model to draw the page on the screen.

> Model is a kind of data structure that you can read and modify. It acts as a live data structure: when it gets modified, the page on the screen is updated to reflect the changes.
> 

```html
<!doctype HTML>
<html>
	<head>
		<title>My home page</title>
	</head>
	<body>
		<h1>My home page</h1>
		<p>Hello, I am Marijn and this is my home page.</p>
		<p>I also wrote a book! Read it
		<a href="http://eloquentjavascript.net">here</a>.</p>
	</body>
</html>
```

*Code has taken from Eloquent JavaScript, page 232*

Suppose you have the following lines in your HTML file. The structure of this page is like the following: 

![page_structure.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1633023965745/2H953OR0O.png)

*Image has taken from Eloquent JavaScript, page 233*

The data structure the browser uses to represent the document follows this kind of shape. Where for each box (or element), we have an object. And this representation is called the **Document Object Model** or **DOM** in short.

## Tree Data Structure

If you will have a look at the structure the browser uses to represent the document, then you will find that it has a combination of branch and nested structure. Two boxes can appear at the same level, a box can contain another box and another box can contain another.

In Computer Science, this kind of structure is known as **Tree.** Where there is a root (in our case, it is the `HTML` element) and the root can have children (also known as **nodes**), which again can have children.

In a Tree, the children can be of two types. One that has other children (known as **internals**) and one that does not have any children (known as **leaves**). The same goes for DOM, the nodes (represented as an Object) for Elements that represent `HTML` tags work as internals, and nodes for text contents and comments work as leaves.

> To get the root of the DOM, you can use `document.documentElement`
> 

## Traversing the DOM tree

![dom.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1633023995935/clE-0ht_9.png)

Each node (that is represented as an Object) in the tree has many properties which we can use to traverse the **Tree.**

Some of the useful properties are 

→ **parentNode:** `node.parentNode` contains a reference to the parent node of the node. for example, `p.parentNode` will give a reference to the `body` node.

→ **childNodes:** Every internal node has this property. It gives an array-like object (NodeList) that contains all its children.

→ **firstChild:** Points to the first child element, or null for nodes without children. 

→ **lastChild:** Points to the last child element, or null for nodes without children.

→ **previousSibling:** Points to the adjacent node, which is the node with the same parent that appears immediately before the node.

→ **nextSibling:** Points to the adjacent node, which is the node with the same parent that appears immediately after the node.

→ **children:** This property is much like as childNodes, but gives only internal children nodes.

![traverse.PNG](https://cdn.hashnode.com/res/hashnode/image/upload/v1633024017883/wylbjk-18.png)

*Image has taken from Eloquent JavaScript, page 235*

While traversing the Tree, whenever you visit a node you can check which type of node it is. This means that the node is a type of `HTML` tag, a text node, or a comment node.

To check this, you can use the **nodeType** property of the node and can compare it with pre-defined constants. Some pre-defined constants that you can use are:

→ **document.ELEMENT_NODE:** To check the node is of the type `HTML` tag. 

→ **document.TEXT_NODE:** To check the node is of the type Text.

→ **document.COMMENT_NODE:** To check the node is of the type Comment.

## Changing the Document

As the document is represented in a Tree-like structure by the browser. So we can add a new node in the Tree, can remove a node from the Tree, and can replace a node with a new node. 

And as we will do the changes in the Tree, it acts as a live data structure which means when it's modified, the page on the screen is updated to reflect the changes.

To modify the tree, you can use various methods that are available to the nodes. Some of the methods are:

→ **appendChild:** We can use with element nodes, to add a new child node at the end of the list of children.

→ **insertBefore:** We can use to insert a new node given as the first argument before the node given as the second argument.

→ **replaceChild:** You can use to replace an old child given as the second argument with a new node given as the first argument.

→ **remove:** To remove a node from its current parent node.

## That's all

That's all for this blog, now you should practice all the discussed properties, to see the live working of them.
Thank you for reading this article, and will love to connect with you. You can find me on [Twitter](https://twitter.com/hsnice16).

The idea of this blog came from the Eloquent JavaScript book. It is a really nice book for beginners. And even if you have experience, you should give it a read. And if you are a beginner then you should definitely give it a read.

Thank you!