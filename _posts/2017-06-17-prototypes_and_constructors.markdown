---
layout: post
title:  "Prototypes and Constructors"
date:   2017-06-17 21:06:46 +0000
---


JavaScript does not contain the typical class construct found in most object oriented languages. This functionality is provided by prototypes. Prototypes are very similar to classes in other languages but the important concepts to remember are that every function in JavaScript has a prototype and the prototype is wher the function inherits properties and methods. I find it helpful to think of the prototype as a mold that can be used to create new objects. Each object will have the characteristics of the mold but can be customized for your needs.

All functions inherit from the Object type. When you create a new prootype that prototype will have the properties and methods of Object. All objects created from that prototype will inherit the prototype's properties and methods as well as those from Object. When JavaScript is looking for a method or property it will first check what is defined on the object itself then look at the prototype and finally check Object.

The constructor is one of two ways to create an object. The other way of creating an object is by using a literal. For example:

var my_name = { first: "Ray", last: "Mulligan"}

To use the constructor you would first create the prototype:

function My_Prototype(first, last) {
  this.first = first
	this.last = last
}

Then create your new object:

var my_name = new My_Prototype("Ray", "Mulligan")

Understanding prototypes and constructors is very important for a JavaScript programmer. Once you understand the concepts, practice with the implementation and you will be much further ahead in gaining JavaScript proficiency.

