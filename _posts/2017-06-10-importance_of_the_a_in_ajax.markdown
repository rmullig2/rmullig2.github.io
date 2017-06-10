---
layout: post
title:  "Importance of the "A" in AJAX"
date:   2017-06-10 04:23:20 +0000
---


As we all know the first A in AJAX stands for asynchronous. Forgetting this can really trip you up. The final two projects required extensive use of AJAX and if you forget that the requests you made are asynchronous then you will be scratching your head wondering why your code does not work.

The issus is that when you execute an asynchronous command then the command will be executed in the background the your program will continue to run. When writing an application using Rails only this was not a concern. One command would execute before the next command started, that changes with AJAX.

The two ways I found to deal with this are first to disable the asynchronous behavior of the command by using the async false option with jQuery. However, this defeats the purpose of AJAX/ The preferred method is to execute the dependent code within a function that runs with the success or done methods of jQuery. This is what I used for my portfolio. The syntax can be tricky for large function with many commands but if you are careful you will find that it performs very well.
