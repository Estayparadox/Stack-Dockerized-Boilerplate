# Dockerized-Node-Stack

This Dockerized app is made in Node.JS. It uses [Semaphore](https://semaphoreci.com) and [Docker Hub](https://hub.docker.com) for CI.
Also, [PM2](https://pm2.keymetrics.io/docs/usage/quick-start/) a production process manager for Node.Js is used.

## Install & Run

To start the application:
```
$> npm start
```

To run a PostgreSQL database with Docker:
```
$> docker run -it -e POSTGRES_PASSWORD=password -p 5432:5432 postgres
```

To create the table:
```
$> npm run migrate
```

To start the application with pm2:
```
$> npm run pm2
```

To run tests
```
$> npm run test
```

To start Docker Compose:
```
$> docker-compose up
```

To run database tests inside the container:
```
$> docker-compose run app npm test
```

To test endpoints with curl:
```
$> curl -w "\n" \
       -X PUT \
       -d "firstName=Bobbie&lastName=Draper" \
       localhost:3000/persons

$> curl -w "\n" localhost:3000/persons/all
```

## Process

To create the directory structure:
```
$> npx express-generator --no-view app
$> cd addressbook
$> npm install
```

To install PostgreSQL node driver and sequilize ORM:
```
$> cd app
$> npm install --save pg sequelize
```

To install JEST:
```
$> npm install --save-dev jest
```

To install PM2:
```
$> npm install --save pm2
```

To build docker container:
```
$> docker build -t app .
```

To run docker container:
```
$> docker run -it -p 3000:3000 app
```

To check running containers:
```
$> $ docker ps
```

To run the migration script inside the container, build docker image, create persistent volume, create the table:
```
$> docker-compose run app npm run migrate
```

To download the image from Docker Hub:
```
$ docker pull YOUR_DOCKER_USERNAME/dockerizing-nodejs-addressbook:latest
```
