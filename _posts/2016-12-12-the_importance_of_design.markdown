---
layout: post
title:  "The importance of design"
date:   2016-12-12 18:59:31 +0000
---


I have found that creating the portolio projects to be a much greater challenge than the programming labs. The big difference is having to come up with your own design for the project. It is much more difficult to have to build something from scratch rather than completing a series of steps already laid out for you.

I have found the best plan for completing the project is to follow the model-view-controller pattern and build your project accordingly. This will help keep your design clean and easy to understand. You don't want to get most of the way through a project and realize that you underlying design is faulty. That will cost you much more time than if you took longer at the beginning to plan out your project. Sometimes in the zeal of wanting to start coding the design phase is not given sufficient attention.

The first step I would suggest is thinking about how your database tables should look. What are the relationships between them and what columns should each hold. I would advise not making excessive has_many and belongs_to relationships. Create only what is necessary for your project, it will make it easier to implement and troubleshoot.

Next you should consider your web pages. How many pages will you be creating? What information will each of them display? What forms and links will be created for navigation? It is best to have all of this planned out in advance.

Finally you need to consider your controllers. What methods need to be created? How are you organizing the methods? I try to separate the methods into different controller files in order to make them easier to read. Using helper methods will allow the code to be more compact and easier to understand.

The importance of design is something that is developed with experience. A poorly designed project will cause a great deal of frustration and time loss. Think through your design and your coding experience will be much smoother.
