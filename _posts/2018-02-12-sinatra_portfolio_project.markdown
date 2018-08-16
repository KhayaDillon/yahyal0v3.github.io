---
layout: post
title:      "Sinatra Portfolio Project"
date:       2018-02-12 14:25:22 -0500
permalink:  sinatra_portfolio_project
---



For my project I created a web app where users can create virtual pets. My inspiration for creating it was remembering the site Neopets. Like some others' first introduction to code I've heard about, Neopets was my first experience playing a little with code. I remember each pet would have their own webpage that you could design if you knew how to edit the html. 


On a difficulty level, I found this project to be easier than the last one--the CLI project. In a way, the most challenging part was setting up. Setting up the gems, file requirements, etc isn't just following a pattern you already know in your head, like the rest of it is. It's more like lines you have to memorize and remember which belongs to which file. It might also be because the curriculum focuses more on having us practice migrations and MVC, then creating the environment and config files ourselves.


After set up, I worked on the database next by creating migrations. A user needed to have a username, password, and could have many pets. A pet needed to a name, birthdate, physical characteristics, and of course, belong to a user. After migrations, then models, one by one, I created application controller methods and their corresponding views. For a type of characteristic that had a limited selection, for example, animal classes (mammal, bird, fish, reptile, amphibian, bug), I created radio buttons with the different options instead of a text boxes.

Most of the problems I ran into were from missing syntax and improper spelling. For example, accidentally writing "<%=ruby code here>" instead of "<%=ruby code here%>". I also had problems with using the patch HTTP verb to create an edit action. I ended up having to use the post HTTP verb, and am still unsure why it did not work.
