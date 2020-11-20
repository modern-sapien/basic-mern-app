# basic-mern-app
This repository is meant to serve as a basic fullstack react application reference for personal projects and cooperative learning

## Goal: Full Stack MERN APP 

## Process
     1. Set up server
        *   create server.js file
        *   npm init -y
        *   npm install express mongoose dotenv if-env

    2.  Build out basic server
        *   server to run on port 3001 to not conflict with react when it runs
    
    3.  After the server has been setup, add create-react-app client on top
        * In the root, run "npx create-react-app client --use-npm"

    4.  Run 'npm install concurrently -D"
    4. Add script: `"client": "cd client && npm run start",' to serve package.json
 
    5.  Add script: `"start-dev": "concurrently \"nodemon --ignore 'client/*'\" \"npm run client\"",' to serve package.json

## 
