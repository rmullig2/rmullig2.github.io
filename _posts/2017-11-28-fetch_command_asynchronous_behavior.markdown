---
layout: post
title:      "Fetch command asynchronous behavior"
date:       2017-11-29 00:29:14 +0000
permalink:  fetch_command_asynchronous_behavior
---


I learned an important lesson today about how the Fetch command works. For example take the following code:

export function MyFunction() {
  return () => {
    console.log('a');
    fetch('http://localhost:3000/test')
    .then(console.log('b'))
    .then(console.log('c'))
    console.log('d')
  }
}

When executed this function will return the following:

a
b
c
d

But what if instead of directly calling the console.log('b') we put it inside a function:

export function MyFunction() {
  return () => {
    console.log('a');
    fetch('http://localhost:3000/test')
    .then(() => console.log('b'))
    .then(console.log('c'))
    console.log('d')
  }
}

This will return

a
c
d
b

Likewise if we enclose console.log('c') inside a function:

export function MyFunction() {
  return () => {
    console.log('a');
    fetch('http://localhost:3000/test')
    .then(() => console.log('b'))
    .then(() => console.log('c'))
    console.log('d')
  }
}

We then get

a
d
b
c

What is happening is that fetch returns a promise which is a method that will eventually return a value. The "then" statements execute after the fetch command. When we are running plain console.log commands then these commands are not dependent on the value returned from the fetch. When the console.log is encapsulated within a function then the function will wait for the value returned by fetch even if it isn't using it.

The asynchronous nature of fetch will cause execution of the program to continue without waiting for those functions to complete. Therefore d is printed before b and c. This can be seen when we display the response from fetch:

export function MyFunction() {
  return () => {
    console.log('a');
    fetch('http://localhost:3000/test')
    .then((response) => console.log('b', response.json()))
    .then(() => console.log('c'))
    console.log('d')
  }
}

Yields

a
d
b Promise {[[PromiseStatus]]: "pending", [[PromiseValue]]: undefined}
c


