# Homework14Homework week 14

This app allows users to create an account, or log in with a previously created account.

It utilizes many coding languages,frameworks, and libraries including:
Bcryptjs
Express
Express-session
Mysql2
Passport
Passport-local
Sequelize

There are several steps you need to take before running the app on your own computer. First you need to create the database in Mysql Workbench named “passport_demo”. Then navigate to the config.js file and add your login info for Mysql Workbench so the app can connect to the database. After, open your terminal and run npm i this installs the necessary packages needed to run the app. Once installed run node server.js to connect to the server. Finally go to http://localhost:8080/ to use the app.

Files

Here I will give a brief explanation of what each file does.

Config

Middleware
Makes sure the user is logged in if not it redirects them to the login page,

config.JSON
Loads the default configuration file and loads default environment configuration and overrides default settings. Then it uses those environment variables and command-line arguments to override data from configuration files.
Passport.js
contains javascript logic that tells passport we want to log in with an email address and password

Models
Index.js
connects to database and imports users log in data
User.js
Sets email and password requirements also creates a custom method to check if an unhashed password matches the hashed password stored in DB. Also creates a hook to hash a new password.

Public

JS

Login.js
Contains login page Javascript functions and redirects to the members page.
Members.js
Preforms GET request to determine which user is being logged in and updates the HTML page
Signup.js
Contains sign up page Javascript functions and creates a post to the sign up route and redirects you if no errors.
Stylesheets

Style.css
Sets margin for the form

HTML

Login.html, members.html, signup.html
Contains HTML code for each respective page.
Routes

Api-routes.js
Conrtains the routes for logging in existing users, creating a new user and logging a user out. Also, creates route for how to handle when a user is not logged in
Html-routes.js
Requires using our middleware to ensure the user is logged in and send them to appropriate html page.

JSON Packages

package-lock.JSON
Tells NPM which specific packages to install
package.JSON
Contains information about the project and defines what packages the project is dependent on.

Server

Server.js
Makes sure required npm packages and passport are declared. Sets up port and creates express app and requires middleware. Utilizes sessions to track user login status and requires routes. Displays a message when successfully connected.
