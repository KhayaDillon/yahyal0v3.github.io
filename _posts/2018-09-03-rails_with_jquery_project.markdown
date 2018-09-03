---
layout: post
title:      "Rails with JQuery Project"
date:       2018-09-03 16:29:48 +0000
permalink:  rails_with_jquery_project
---


For my Rails with JQuery front-end portfolio project, I used Ajax to create more dynamic functionality to my reading list manager application. The purpose of the web application was for users to be able to keep track of the books they were reading. 

For this project, my plan was to add a user profile page. At the bottom of each file would be a user’s shelves button, that when clicked, would render the index of the shelves in a table. The user could then click on one of the shelf names to render the show of the shelf in a table. The table would have one table data (td) per table row (tr) to make it resemble a bookshelf. In the shelf show table, the bottom rows would have a back bottom and next bottom so the user could move onto to the next show of shelf.

One of the major problems I ran into was making it so one of my forms could update using Ajax more than once. For the assignment we were required to have a ‘form to create a resource and render the response without a page refresh.’ I easily did this with my create new shelf form, but decided my shelved_book update form should have it, too, since it was better suited for it. The main dead end I ran into was that when a shelved_book updated, getting moved to a different shelf, if the user tried to move it yet again, nothing would happen. I had to schedule two meetings to try to get this solved. 

It was only after the second meeting and gaining a better understanding of the issue was I able to solve the problem independently. Since it was a lot of html code being used to create each shelved_book div, I was using a handlebars template. Even though the html was exactly the same as the one being produced by rails, for some reason when clicking the update button from the code rendered through handlebars, the function listening for the click was not getting executed at all. What I ended up doing was adding a onclick event handler to the handlebars template one. Now when I clicked the update button, I was led to the JSON because event.preventDefault was only being executed for the initial rails produced html. Adding an event.preventDefault into the function that would only execute if the event.type was from the handlebars html (‘click’, instead of ‘submit.’) solved that problem.

