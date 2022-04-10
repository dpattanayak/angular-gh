# Deployment

    1. Github Pages
    2. Firebase
    3. Heroku

### Github Pages

- Create a repository on [Github](https://github.com/) 
- Commit and push local code to remote repository

`sudo npm install -g angular-cli-ghpages`

`npm run deploy:gh`

> Successfully published via angular-cli-ghpages! Have a nice day!


### Firebase

- Create Project on [Firebase](https://console.firebase.google.com/)

`sudo npm install -g firebase-tools`

`firebase login`

> ✔  Success! Logged in as dpattanayak30@gmail.com

`firebase init`

- Which Firebase features do you want to set up for this directory? Press Space to select features, then Enter to confirm your choices.
- Select "Hosting" by clicking spacebar then select project and other options.

> ✔  Firebase initialization complete!

`npm run deploy:firebase`

To solve navigation problem add the following to firebase.json

    "rewrites":[
      {
        "source":"**",
        "destination":"/index.html"
      }
    ]

> ✔  Deploy complete!

Project Console: https://console.firebase.google.com/project/angular-f576a/overview

Hosting URL: https://angular-f576a.web.app


### Heroku

- Create an app in [Heroku](https://dashboard.heroku.com/apps) or Using CLI "heroku create"
- Then move the important packages from devDependencies to dependencies in package.json like (@angular/cli, @angular/compiler-cli, typescript etc)
- Add a Node / Express server for hosting the dist/index.html file

`heroku login`

`heroku git:remote -a angular-f576a`

`git push heroku master`

`heroku open`