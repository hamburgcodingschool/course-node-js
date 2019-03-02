# course-node-js

Course material for the trainer.


## Preconditions

- web application with vanilla JavaScript
- node installed, running in VS Code
- http server running


## Session 1

Node Runtime
- what is node?
- what is that server that is already running?
- frontend, backend

NPM
- what is npm?
- mention alternatives (e.g. Yarn)
- package.json
- modules, imports
- dependencies

Project Setup
- installing packages
- project structure

Express.js Framework
- explain: what is it? why do we need it?
- deliver a first website (hello world)
- migrate our application to be delivered by node/express

Code checks
- tooling: scripts

Homework:
- install MongoDB


## Session 2

Database
- Mongo DB
- Task: set up Mongo DB

Task:
- connect node to Firebase
- migrate database from Firebase to local DB

Mention:
- node is not suitable for tasks like migrating data from one database to another

Save data to Mongo:
- save lat long, text, image url
- save images

Create an API:
- load posts with images from MongoDB
- provide express endpoints

If there is time:
- authentication with Passport


## Session 3

Asynchronous calls
- callbacks
- Promises

Task:
- rewrite app to use async calls

Event Queue

Mention:
- async-await


## Session 4

Connect frontend to backend
- explain express: what is it, what does it do?

Express:
- rendering HTML: templates
- connect to existing endpoints

Task:
- rewrite our app to use router
- 4 pages:
  - map
  - login
  - post
  - list view
  

## Session 5

Deployment
- Heroku / AWS?
- prepare the build
- package and deploy
- database: dump (!)

Favicon
- how to generate one
- where to put it

404 page
- create your own

If there is time:
- environments: stage, prod


## Session 6

Architecture
- REST API endpoints
- static documents
- best practices

Task:
- preparing for Vue.js course:
- delivering static html pages at certain path
- router: front controller


## If there is still time

- Authentication with passport
- user management
- user groups (admin, visitors, authors)


