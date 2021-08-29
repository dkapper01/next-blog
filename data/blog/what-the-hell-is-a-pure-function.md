---
title: 'What the hell is a Pure Function?'
date: '2020-07-19'
tags: ['javascript', 'react', 'programming']
draft: false
summary: 'React is pretty flexible but it has a single strict rule. All React components must act like pure functions with respect to their props.'
authors: ['default']
---

I was reading the React docs and came across this

> React is pretty flexible but it has a single strict rule.
> All React components must act like pure functions with respect to their props.

Unfortunately, I didn’t know exactly what a pure function was, and since I’m a react developer I thought it would be a good idea to know what the hell is a pure function. This is why I decided to write this post.

A pure function is simply described as:

1. Its return value is the same as the value being passed as props.
2. Its evaluation has no side effects such as changing valuable outside the function.

A pure function is like a math problem. 2 + 2 is always 4. That problem does not have any side effects. It will always return 4. You will never change the value of 2 and get a different answer.

Here is an example, of a function that is not a pure function. It has a side effect and that side effect is it changed the global array variable.

```js
const array = [1, 2, 3, 4]

function AddElementToArray(a, element) {
  a.push(element)
}

AddElementToArray(array, 5)
```

Array now equals [1, 2, 3, 4, 5]. If it was a pure function the array variable would never change but the return value from the function would by [1, 2, 3, 4, 5].

How you can my make the above function a pure function is like this:

```js
const array = [1, 2, 3, 4]

function AddElementToArray(a, element) {
  return [...a, element]
}

AddElementToArray(array, 5)
```

The return value is the same as the first function but it does not change the global array variable or in other words, there are no side effects and can now be called a pure function.

A pure function should always return the same value regardless of how many times it is executed if the input remain the same. It should not add on to the previous value or change any other value.
