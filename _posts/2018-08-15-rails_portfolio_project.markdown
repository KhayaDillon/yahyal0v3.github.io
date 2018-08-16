---
layout: post
title:      "Rails Portfolio Project"
date:       2018-08-16 03:26:25 +0000
permalink:  rails_portfolio_project
---


For my Rails portfolio project, I created a reading list manager. The purpose of the application was for users to be able to keep track of books they plan to read, were reading, and had finished reading. The plan was for the website to have a list of books--in an ideal, fully realized version, a list of all books in existence. The user could add books from this list to one of their shelves. Every user would have a default 'Reading' and 'Finished Reading' Shelf, but could create additional ones to categorize their books as they saw fit. Aside from organizing them this way, the user would also be able to keep track of what page they were on and change the book's status. Statuses would include 'Currently Reading', 'Plan to Read', 'On Hold', 'Finished', and 'Dropped'.

To get started, I knew I would need to create a books index to show all the books. Under each book would be a small form--a dropbox with the current user’s shelves, so users could add it. The shelves index page would list each of the user’s shelf. Each shelf would have an edit and delete link and list its books. Each book would have an edit form so the user could adjust the status, shelf, and current page.
    
The first main thing I did was create the migrations and models. A user had many shelves, and many books through shelves. Books had a title, author, genre, page count, current page, and status. Shelves had a name and belonged to a user. Then, instead of creating the books manually, I found a website that had the book details I needed and created a scraper.

I ended up running into quite a few problems and obstacles I had to overcome.

There were a couple of things I realized needed changing as I worked on the actual project. For example, figuring out the Books and Shelves’ proper relationship was tricky. Thinking about it conceptually, my mind wanted to think a book belongs to a shelf, and a shelf has many books. But from how the associations worked from the previous Flatiron Store project, I knew that when a user took out a book to put on one of their shelves, it would be easier to work with a join table of Books and Shelves. Then I realized Books should not have the current page and status attributes, because these attributes would be blank until put on a shelf, and having empty columns was not good database structuring. Even conceptually, a book wouldn’t have a current page and status until it was taken out, so it would more sense to have these attributes in the Shelved Books join table.

The hardest obstacle I had to overcome was sorting out the books’ three related attributes--the current page, status, and shelf. When the current page was set on the last page, for example, the status would have to be changed to ‘Finished’ and the shelf could not be on the default ‘Reading’ shelf. It was a lot of conditional to work with. I had to account for every possible pairing. A troublesome user setting the shelf to ‘Finished Reading’, the status to ‘Plan to Read’ yet the current page to 40, for instance.I hadn’t realized how much harder I had made it on myself, but once I had started working on the conditionals I did not want to stop and abort. It was a case of wanting to it through since you already started. Eventually making notes of what attributes and circumstances the if statements were filtering helped me. This probably would have been easier with Javascript, as the page would not have to reload to check if the current pairings were valid. 

Initially I had all of the logic for this sorting job jumbled up in the controller. I cleaned it up as much as I could, but knew something was off. It was too ugly. It wasn’t until skipping a head and doing some of the Javascript lessons that I realized I had to break it up into pieces by separating it into different methods. Only thinking of Models, Views, and Controllers, I hadn’t realized I could create a class to deal with this logic. If I had started with smaller, separate methods instead of long blocks on logic, figuring out errors probably would have been much easier. 

