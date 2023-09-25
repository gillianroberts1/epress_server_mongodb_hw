# Homework: Full Stack Games Hub App

### Learning Objectives

- Understand the relationship between client, server and database
- Be able to navigate a codebase that you haven't written

## Brief

Your boss has asked to you look over the codebase of a full-stack JavaScript application. The front-end is written in JavaScript using React, the back-end uses an Express server and a MongoDB database. Your task is to make yourself familiar with the codebase.

The application includes a README.md with instructions on running the application.

![Overview of the tech stack and tooling with commands](images/tech_stack_with_commands.png)

*Overview of the tech stack and tooling with commands*

*EDIT: Frontend is now written in React with the command to run `npm start`*

## MVP

### Task

Draw a diagram showing the dataflow through the application starting with a form submission, ending with the re-rendering of the page. This will involve a multi-direction data-flow with the client posting data to the server and the server sending data back to the client with the response. Detail the client, server and database in the diagram and include the names of the files involved in the process.

### Questions

1. What is responsible for defining the routes of the `games` resource?

Answer - create_router.js   

2. What do you notice about the folder structure?  Whats the client responsible for? Whats the server responsible for?

Answer - 
Client: 
is the front end part of the app.
Server: 
seeds.js is sending the data to mongodb.

create_router.js is defining the routes for interacting with the db.

server.js is setting up the DB connection

3. What are the the responsibilities of server.js?

Answer- uses the express framework to create an api for interacting with mongodb

4. What are the responsibilities of the `gamesRouter`?
Answer - an express router is to handle the the http requests related to a specific resource. It handles CRUD operations for the api within mongodb.

5. What process does the the client (front-end) use to communicate with the server?

Answer - the HTTP method - GET< POST< PUT< DELETE. 

6. What optional second argument does the `fetch` method take? And what is it used for in this application? Hint: See [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) on the MDN docs

Answer - The optional second arguement used is an object, to customise the request. In postGame, POST specifies that a POST request should be made.
In deleteGame the DELETE option specifies that a delete request should be made.

7. Which of the games API routes does the front-end application consume (i.e. make requests to)?

 Answer - GET all, GET by ID, POST, DELETE by ID, PUT by ID.

8. What are we using the [MongoDB Driver](http://mongodb.github.io/node-mongodb-native/) for?

Answer - it is for Node.js to connect to the mongodb and perform various db functions. Over all for storage and retreival of data.

Database connection (mongoclient) to establish a conection with the mongodb database.

Database operations (CRUD) - the mongodb driver is used to perforrm CRUD operations. createROuter handles these operations

mongodb ObjectId - we use this constructor to convert srting based ID's to mongodb ObjectId's.



## Extension

Why do we need to use [`ObjectId`](https://mongodb.github.io/node-mongodb-native/api-bson-generated/objectid.html) from the MongoDB driver?


Answer - 
uniqueness - values are guaranteed to be unigue withing a collection. and avoids conflicts when inserting new documents

Efficiency - values are genrated with a timestapm, machine indentifier, process identifier, and a random value. They can be soreted by theior creation time.

AUtomatic Generation simpioefies the process of creating new documents

Standarisation - objectid is a standard way to represent unique indentifiers.  It is widely used and recognised.


It allows you to perfrom precise queries.

Add to your diagram the dataflow for removing a game.
