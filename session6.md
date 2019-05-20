Cookies
- how does it work
- same origin policy
- task for today: implement user session
- with JSON web token

Passport:
- node.js library for session handling
- http://www.passportjs.org/
- "strategies": logins for Facebook, Google, Twitter...

Recap Middleware
- what is a middleware
- sequence of processing
- passport has 2 middlewares

User handling
- you need to tell passport how to handle users
- e.g. save into database
- we need to tell passport how to save data, and which data
- serialize / deserialize

Background security:
- don't save passwords in clear text into the database
- rather use bcrypt https://www.npmjs.com/package/bcryptjs 
- save the hash instead

Task:
- show login form if user is not signed in

