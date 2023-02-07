## Docker Compose - Run multiple Docker containers

This app shows a simple user profile app set up using

- index.html with pure js and css styles
- nodejs backend with express module
- mongodb for data storage

All components are docker-based

### Technologies used:

Docker-compose, Node.js MongoDB, MongoExpress,HTML, CSS, JavaScript

### Project Description:

1- Write Docker Compose file to run MongoDB and MongoExpress containers.

2- Run Nodejs application in Docker container and connect to MongoDB database container locally.

3- Run MongoExpress container as a UI of the MongoDB database.

### With Docker Compose

#### To start the application

Step 1: Create the compose yaml file

![Alt text](app/images/compose-yaml.png?raw=true)

Step 2: start mongodb and mongo-express by docker compose

    docker compose -f docker-compose.yaml up

_You can access the mongo-express under localhost:8080 from your browser_

Step 3: in mongo-express UI - create a new database "my-db"

Step 4: in mongo-express UI - create a new collection "users" in the database "my-db"

Step 5: Go to `app` directory of project

    cd app

Step 8: Add a " .env" file into the app directory of project and fill the environment variable
![Alt text](app/images/env_file.png?raw=true)
Assign "my-app" to DATABASE in .env file
Assign "users" to COLLECTION in .env file

Step 9: Start your nodejs application locally inside the app directory.

    npm install
    node server.js

Step 10: Access you nodejs application UI from browser

    http://localhost:3000

Step 11: to Stop mongodb and mongo-express containers by docker compose

    docker compose -f docker-compose.yaml down
