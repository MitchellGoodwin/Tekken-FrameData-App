# Tekken Frame Data App

## Project Description

Hello, and welcome to my app. As a project to explore and practice Rails, I wanted to make a website centered around something I love: fighting games, and sepcifically the game Tekken 7. All fighting games have characters with a lot of moves that players study obsessively to inorder to inform their desicion making mid-match. The characteristics for each move are broken down into characteristics that each move has and referred to as frame data.

I want to create a site for users to look up frame data for each character, with an attached forum to discuss the ins and outs, while also acting as a place to community build.

## Technologies Used

* Ruby on Rails
* Bulma
* API
* CSS
* Bcrypt


## Installiation

* Clone the repo to your computer
* Navigate to the directory and run `bundle install`
* run `rails db:migrate` and `rails db:seed`. This should take a couple seconds. The api has to pull 8460 moves and 45 characters.
* run `rails s`
* The site should be live at http://localhost:3000/

## Schema

My model schema is this:

A character <-> has many moves, that belong to a character

A forum <-> belongs to a character

A forum has many <-> posts and a post belongs to a user

A user has many <-> posts and a post belongs to a user

A favorite belongs to a User, and a character

## User Stories

My basic user stories are:

* A user can look up characters and their moves
* A user can make posts on a forum related to a specific character
* A user can edit and delete their own posts
* A user can read other user's posts, and look at those user's pages
* A user can edit thier own page
* A user can favorite a character and have a link to that character's page show up on thier page

## Walkthrough of Site Functionality:

The homepage for the app shows a welcome message, as well as login and signup buttons. The user can use either one to login, the signup will make a new user class for that user. A user must have a username and password to sign up. After login, the site will redirect back to the page the user was on before. When seeing the home page while logged in, the user will see a message to them and a logout buttons.

At the top of the page, on the layout, there will always be buttons to the home page, character index page, and forum index pages. There are also login, signup, logout, and profile page buttons for the user depending on if they are logged in or not.



![](app/assets/images/welcome.png)



The character index page has all the characters images laid out in a grid, with buttons with their names on it that are links to that individual character's show page.



![](app/assets/images/CharacterIndex.png)




The individual character's show page has all of the character's moves listed in table form. Each move has the right real world properties pulled from an API. At the top of the page their is a link to the character's forum, and, if the user is logged in, a button to either favorite or unfavorite a character.



![](app/assets/images/CharacterShow.png)



The forum index page has all of the forums listed in lines. Each line has a link to that forum, as well as the latest post in that forum.




![](app/assets/images/ForumIndex.png)




For the forum show pages, it displays the last ten posts made on that forum. If the user is logged in, the page has a form to make a new post on that forum at the bottom. A post cannot have more than 500 characters. If the logged in user has any posts on that page, they have a button to the right of that post to go to an edit form for that post.




![](app/assets/images/ForumShow.png)




On an individual user's profile page it shows their picture, their username, their location, and their bio. It also has a list of all of their favorite characters, with links to that character's show page. If the user for that page is the currently logged in user, there will also be a button to go to an edit form for the user.




![](app/assets/images/Profile.png)





## Code Examples





## Difficulties

* Learning Bulma, and by extension css, was a challenge for me, as I've had no real previous experience in either before this project and had to learn on my own. I'm happy with how it turned out for a first try, and I feel much more comfortable with both technologies. There's still some things I wish could be better about my styling, and if there's a convention to stick to, I did not follow it at all.

* In extension to the above point, learning how to use forms without rails helper methods was a little difficult. But overall not too bad. Eventually I found out you can partially implement them with bulma styling so it was a small waste anyway, but that's how it is sometimes.


## Stretch Goals

I'd honestly like to do a lot, here is what I have in mind. I'm prepared to not be able to do all these, but it would be neat to do.

* Limit how many posts show up on a forum page. Add buttons to load the next or previous batch of however many.

* Add search functionality for moves

* super fancy: Let users submit change requests for character pages/ move data. The admin would get an email about the request, and can see pending requests on an admin page. I need to research this. 

## Credits

* [rbnorway](https://www.example.com) - The site my api pulled from for the Tekken data.

* [tkshehan's Tekken API](https://github.com/tkshehan/t7-server) - The API I used to get my data.