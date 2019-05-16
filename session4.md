## Session 4

Goal for today:
- we want to dynamically generate websites with Node.js

Fix and dynamic parts:
- fix: layout
- dynamic: what changes, e.g. shopping cart etc.

Task:
- think about your app:
- what is dynamic, what is fix?

Template engine:
- creates HTML 
- why not static html?
- to make it dynamic
- divide into presentation and logic
- today we will have a look at `handlebars`

Task:
- install express-handlebars
- https://www.npmjs.com/package/express-handlebars
- require handlebars

Explain:
- we map `.handlebars` file extension to handlebars library
```
exp.require('handlebars', exphbs());
exp.set('view engine', 'handlebars');
```

Show: 
- `index.html` layout with:
```
{{{body}}}
```
- `home.handlebars`

Task:
- build that in your app
- output: some `<h1>Home</h1>`


