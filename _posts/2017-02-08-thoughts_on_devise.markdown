---
layout: post
title:  "Thoughts on Devise"
date:   2017-02-08 04:37:39 +0000
---


Just finished up the last lab before the Rails portfolio project so I think this is a good time reflect. The most difficult part of the Rails portion of the course for me was working with Devise. I'll go over some of my observations and lessons learned here.

The biggest thing that jumped out at me was how the Devise gem hides much of the controller and view information from the developer. It makes it very difficult to troubleshoot problems using the usual methods. I found myself struggling to understand how the program was flowing and where the errors were occurring.

I believe the best lesson I learned from reading on the subject was that it is best not to add attributes to the user method if possible. It is very difficult when you try to update or delete user attributes and they appear not to change. I found that creating another model and linking it to use worked the best.

Onto the portfolio project, it looks to be very rewarding.
