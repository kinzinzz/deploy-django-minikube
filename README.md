# Django Poster Demo App

Django project that contains a simple app that allows users to post content to a web page.

The purpose of this project is to provide students with a simple working Django app in order to demonstrate deployment of the app using various methods.

This project includes the following:

 * Uploading and displaying media/static files
 * Django admin
 * Docker compose setup for local deployment


## Get started

This project contains two docker compose config files:

 1. `docker-compose.yml` is the main file, used for local development/testing of the project.
 2. `docker-compose-deploy.yml` is a deployment simulation, which is used to show how a deployment would work using Docker.

### Starting local development server

To test this project locally, ensure you have the following installed:

 * [Docker/Docker Desktop](https://www.docker.com/products/docker-desktop/)

Then, run the following:

```
docker-compose up
```

This will create the project, and you should be able to login using [http://127.0.0.1:8000](http://127.0.0.1:8000).

To create a superuser, run:

```
docker-compose run --rm app sh -c "python manage.py createsuperuser"
```

To clear all data (including database), run the following:

```
docker-compose down --volumes
```

### Running deployment simulation

To run the deployment simulation, first copy the config:

```
cp .env.sample .env
```

Then open `.env` and modify the configuration values appropriately.

Next, run the following to start the deployment simulation:

```
docker-compose -f docker-compsoe-deploy.yml up
```

This should start a server and support static/media files through the NGINX proxy. You can access the server on [http://127.0.0.1:8080](http://127.0.0.1:8080).

### CMD

docker-compose run --rm app sh -c "python manage.py createsuperuser"

minikube start --nodes 3

minikube dashboard

kubectl apply -k deploy/

kubectl get deployments

kubectl get pods

docker buildx build -t django-app:latest .

docker buildx build -t django-proxy:latest proxy/

minikube image load django-app:latest

minikube image load django-proxy:latest

docker context use default

kubectl get services

kubectl exec -it django-666595d456-fhzk5 -c app -- python manage.py createsupuser
