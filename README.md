# dockerizing-djangoapp

OBJECTIVE

dockerizing a django application

Why should you use Docker?
Docker is a product that offers hardware virtualization at the Operating System (OS) level. This ability allows developers to package and ship software and its dependencies in order to distribute as containers.

Requirements:

Dockerfile
Docker-compose file
Requirements.txt file
Proficiency in Django development

Steps:

1:
To start, run the below commands to get your Django app setup.

    django-admin startproject djangoapp
    python3 manage.py startapp app
    
    define views of django app
2:
A critical step that many forget is to set up the ALLOWED_HOSTS to ‘*’ in order to allow access to the Django application from any IP. The code snippet is shared   below

   ALLOWED_HOSTS = [‘*’]

3: 
In your project root, create a file named Dockerfile and open it.

4:
Add the content to the Dockerfile.
The Dockerfile starts with a Python 3 parent image. The parent image is modified by adding a new code directory. The parent image is further modified by installing the Python requirements defined in the requirements.txt file.

5:
Create a requirements.txt in the project directory.
This file is used by the RUN “pip install -r requirements.txt” command in the Dockerfile.Add the required software to the file.

6:
Create a file called docker-compose.yml in the project directory.
The docker-compose.yml file describes the services that make the app. In our case, the “web” and “DB” services are web server and database respectively. The compose file also describes which Docker images these services use, how they link together, any volumes they might need to be mounted inside the containers. Finally, the docker-compose.yml file describes which ports these services expose.

7:
Running the app in Docker
        Build the image:sudo docker-compose build
        
        Run the image: This is done using the docker run command. This will convert the built image into a running container
                       sudo docker-compose up
                       
        
        

