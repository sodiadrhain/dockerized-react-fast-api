# Backend - FastAPI with PostgreSQL

This directory contains the backend of the application built with FastAPI and a PostgreSQL database.

## Development Environment

### Setup

### Prerequisites

- Python 3.8 or higher
- Poetry (for dependency management)
- PostgreSQL (ensure the database server is running)

### Running App locally

Clone the [repository](https://github.com/sodiadrhain/dockerized-react-fast-api.git) and proceed with the instructions below.

## Project setup

Goto Backend path

```
 cd backend
```

Then run 

```
curl -sSL https://install.python-poetry.org | python3 -
```

Add Poetry to your PATH (if not automatically added):

### Install dependencies using Poetry

```
poetry install
```

### Set up the database with the necessary tables

```
poetry run bash ./prestart.sh
```

### Run the backend server
```
poetry run uvicorn app.main:app --host 0.0.0.0 --port 8000
```

## Running as Docker Container

Ensure you have docker installed to do this, to check if docker is installed correctly run:

```
docker -v
```

and you should see the version of you installed docker application.

**From within the project directory (/backend) run the following:**

```
docker build -t backend_fast_api_image:latest .
```

to build image and container for app, when done, run:

```
docker run -p 8000:8000 --name backend_fast_api -d backend_fast_api_image:latest
```

when this is done, app will basically start on port `8000`.

```
localhost:8000
```

### Viewing the running ports

Open a new terminal window and run the following command:

```
docker ps
```

You will be given a printout showing your running containers. Part of the printout should contain something like this:

```
.....   0.0.0.0:5173->8000/tcp,     backend_fast_api

```

This tells you that the various machines exist "locally" at 0.0.0.0 and that the exposed web port have been mapped to port 8000.

### Stopping Container

To stop the docker development environment, issue the following command from the project root:

```
docker container stop backend_fast_api
```

This will stop all the container and related to this project.

### Starting Container

To start the docker development environment another time run:

```
docker container start backend_fast_api
```

This will start the container again.

### View the Home Page

To load the homepage of the app, visit the url below in a browser:

    http://0.0.0.0:8000

Thus your adventure begins... The project is up and running.

Ensure you update the necessary configurations in the `.env` file, particularly the database configuration and the restart the container.


## Deploying as python app - Manually

You can follow the steps below from any of the host platforms you wish to use.

Plaforms include:  [Heroku](https://devcenter.heroku.com/articles/getting-started-with-python?singlepage=true), [Render](https://docs.render.com/deploy-fastapi).


## Deploying as Docker App

You can deploy to AWS EC2 as a docker app.

First setup an AWS Linux environment, you can use the `Amazon Linux VM`.

Next Install GIT and Docker into the environment. 

Then clone this repository and cd to the frontend, now follow the [Running as Docker Container](#running-as-docker-container) steps above. the app should start, with everthing being okay.

Now visit: `http://<public-ip-address>:8000` to see the app running.

You can also deploy as Docker file on [Heroku](https://devcenter.heroku.com/articles/container-registry-and-runtime) and [Render](https://docs.render.com/deploy-an-image).

