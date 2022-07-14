---
title: "Deploy web app with netlify and heroku"
header:
  image: /assets/deploy.png
categories:
  - Deployment
tags:
  - Netlify
  - Heroku
  - Deployment
---

I'm going to deploy my web application with Netlify and Heroku which provide free plan for an individual project. These can be alternative way to show my projects that I'm going to develop so that everyone can access to public url to see my projects. This blog is for exploring how to implement my project using Netlify and Heroku for front-end and back-end respectively. I'm going to record all errors in this blog while implementing the project.

Before I go try to deploy, I need to understand a few terms.

- Static Site: A static site is made up of webpages created using HTML,CSS and JS. Every pages are stored in a single HTML file, and the HTML file is delivered from the server.

- Back-end app: The back-end is the server-side of a web application which user can't interact with directly. The back-end stores and organizes data to allow the front-end of an app to work.

## Netlify (Front-end)

- My client folder in project will be hosted on Netlify

## Heroku (Back-end)

- My server folder in project will be hosted on Heroku

## Steps

1. Install the Heroku CLI
2. Login to heroku

- In the root directory, `heroku login` in terminal.

3. Create `Procfile`

- In `/server`, create a new file named `Procfile` without any extention and type `web: node dist/main.js`

4. Add version of engines

- Add

```
"engines": {
    "node": "14.x",
    "npm": "6.14.7"
},
```

in `server/package.json` file.

5. Change port(?)

6. Create a remote connection with Heroku

- Make sure I'm in the root directory and type `heroku git:remote -a mern-social-login`
  This process will create a remote connection with Heroku and create a branch.
  6-1. Error message

```
Jonghans-MacBook-Pro:mern-social-login jonghanpark$ heroku git:remote -a mern-socail-login
›   Error: Couldn't find that app.
›
›   Error ID: not_found
```

Let's check the apps by typing `heroku apps`

```
Jonghans-MacBook-Pro:mern-social-login jonghanpark$ heroku apps
=== pjh843@gmail.com Apps
mern-project-manager
mern-stack-project-manager
still-inlet-68127
```

I don't have app on Heroku named mern-social-login, so I need to create an app on Heroku first. 7. Push my server code

- `git subtree push --prefix server heroku master`
  server is the folder for backend
  7-1. Error code h10
  To check what the error is, take a look at several things down below.
  7-1-1. Check Procfile

7-1-2. Check Heroku environment variables
`heroku run printenv`

7-1-3. Missing required scripts
