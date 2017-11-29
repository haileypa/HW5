# SI 364 - Final Project questions

## Overall

* **What's a one-two sentence description of what your app will do?**
My app will allow users to search for beers and breweries. If they are logged in, they will be able to save beers and breweries they have searched and view them later. 

## The Data

* **What data will your app use? From where will you get it? (e.g. scraping a site? what site? -- careful not to run it too much. An API? Which API?)** Data about beer and breweries from the brewerydb API

* **What data will a user need to enter into a form?** The create account form will require a username, password, email, and age. The login form will require the user to enter username and password. The search beer for will require the user to enter a beer. The search brewery form will require the user to enter a brewery.

* **How many fields will your form have? What's an example of some data user might enter into it?**
(same as above) The create account form will require a username, password, email, and age. The login form will require the user to enter username and password. The search beer for will require the user to enter a beer. The search brewery form will require the user to enter a brewery.

* **After a user enters data into the form, what happens? Does that data help a user search for more data? Does that data get saved in a database? Does that determine what already-saved data the user should see?** After a user creates an account, they will be able to search and save beers and breweries. If a user logs in, they will be able to view previously saved beers and breweries as well as search for and save new ones. If a beer or brewery is entered, it searchs through the brewerydb api to find a match and provide info.  

* **What models will you have in your application?**
There will be models for users, beers and breweries as well as associations between users and beers, and users and breweries.

* **What fields will each model have?**
Users: id, username, password, email, age
Beers: id, name, abv, description, style
Breweries: id, brewery, website, description


* **What uniqueness constraints will there be on each table? (e.g. can't add a song with the same title as an existing song)**
Users can't have the same username or emails
Beers can't have the same name
Breweries cant have the same name
Users cant save a brewery or beer they have already saved

* **What relationships will exist between the tables? What's a 1:many relationship between? What about a many:many relationship?**
user_beers: user_id, beer_id
user_breweries: user_id, brewery_id

* **How many get_or_create functions will you need? In what order will you invoke them? Which one will need to invoke at least one of the others?**
3 - get_or_create_user, get_or_create_beer, get_or_create_brewery
get_or_create_beer and get_or_create_brewery will need get_or_create_user to get the user_id it is associated with
## The Pages

* **How many pages (routes) will your application have?**
home/login, create account, search, beer info, brewery info, view saved beers, view saved breweries, error pages (404, 500, 405, etc) ~12

* **How many different views will a user be able to see, NOT counting errors?**
7 if logged in, 3 otherwise

* **Basically, what will a user see on each page / at each route? Will it change depending on something else -- e.g. they see a form if they haven't submitted anything, but they see a list of things if they have?**
Homepage - Login(username/password/submit) or create account or contine without logging in
create account - enter username, password, email, age, submit
search page - If logged in: allows to view saved beers, saved breweries, or search for beers or breweries. Otherwise, search beers or breweries
view saved beers - list of saved beers with their info. options to remove item or email list
view saved breweries - list of saved breweries with their info. options to remove item or email list
beer info - beer name, abv, description, style. If logged in, option to save
brewery info - brewery name, website, description. If logged in, option to save


## Extras

* **Why might your application send email?**
Email user notifying when beer/brewery has been added or removed from list. Also email list of saved beers/breweries if user chooses.

* **If you plan to have user accounts, what information will be specific to a user account? What can you only see if you're logged in? What will you see if you're not logged in -- anything?** Users will be able to save beers/breweries and email them. if not logged in, users can still search beers and breweries. 

* **What are your biggest concerns about the process of building this application?**
Making it too complicated. 
