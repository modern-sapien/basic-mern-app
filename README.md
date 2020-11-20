# basic-mern-app
This repository is meant to serve as a basic fullstack react application reference for personal projects and cooperative learning

## Goal: Full Stack MERN APP 

## Process
    1. Set up server
        *   create server.js file
        *   npm init -y
        *   npm install express mongoose dotenv if-env path

    2.  Build out basic server
        *   server to run on port 3001 to not conflict with react when it runs
    
    3.  After the server has been setup, add create-react-app client on top
        * In the root, run "npx create-react-app client --use-npm"

    4.  Run 'npm install concurrently -D"

    5. Add script: `"client": "cd client && npm run start",' to serve package.json
 
    6.  Add script: `"start-dev": "concurrently \"nodemon --ignore 'client/*'\" \"npm run client\"",' to serve package.json

    7. In order to make API calls to our backend development server, we have to add a proxy to our client side package.json. This is for local development only
    "proxy": "http://localhost:3001",

    8. Testing and validation
        * Install axios in the client directory
        * Make an API call to the "/api/config/" route and log it to the console.

    9. Update the scripts object
````javascript
    "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1",
        "start": "node server.js",
        "start:prod": "if-env NODE_ENV=production && npm run start:prod || npm run start:dev",
        "start:dev": "concurrently \"nodemon --ignore 'client/*\" \"npm run client\"",
        "client": "cd client && npm run start",
        "install": "cd client && npm install",
        "build": "cd client && npm run build",
        "heroku-postbuild": "npm run build"
    },
````
    10. Add build folder static & route to server.js

````javascript
        app.use(express.static("client/build"));
````

````javascript
        app.get("*", (req, res) => {
        res.sendFile(path.join(__dirname, "./client/build/index.html"));
        });
````