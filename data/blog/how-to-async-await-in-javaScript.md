---
title: 'How to async await in JavaScript'
date: '2021-08-23'
tags: ['javascript', 'programming']
draft: false
summary: 'Async functions and the await keyword are a new addition to JavaScript. In my opinion, it makes your code cleaner and easy to read by avoiding the need to create a promise chain.'
authors: ['default']
---

Async functions and the await keyword are a new addition to JavaScript. In my opinion, it makes your code cleaner and easy to read by avoiding the need to create a promise chain.

You would create an async function when you are requesting data from a server. To create an async function you must with async at the beginning of the function.

```js
const hello = async () => {
  return 'Hello'
}
```

That not doing much so let's add the fetch() API inside the function.

```js
let hello = async () => {
  fetch('https://jsonplaceholder.typicode.com/todos/1')
}
```

Now we don't know how long it's going to take to receive the data. Let's add await keyword in front of the fetch() API so the code can go on and do other things while it's fetching the data.

```js
const hello = async () => {
  let response = await fetch('https://jsonplaceholder.typicode.com/todos/1')
}
```

We need to turn that data into JSON so let's use .json() function which also returns a promise. If it returns a promise we will have to write another await keyword.

```js
const hello = async () => {
  let response = await fetch('https://jsonplaceholder.typicode.com/todos/1')
  let data = response.json()
  return data
}
```

While we are at it we should add so error handling.

```js
const hello = async () => {
  try {
    let response = await fetch('https://jsonplaceholder.typicode.com/todos/1')
    console.log(response.ok)
    let data = response.json()
    return data
  } catch (err) {
    console.error(err)
  }
}
```
