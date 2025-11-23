# docker-and-kubernetes-learning
Notes and codes from the Coursera course 

## Installing Docker


## Running containers

nginx is a web server:
https://hub.docker.com/_/nginx

--> `docker pull nginx`
`docker run nginx`

`docker ps` shows the Docker processes currently running

`docker run -d nginx` --> Starts container in detached mode, then the next line is the process hash which will match what you see with `docker ps`
Docker also gives running processes a more human-readable name, e.g. "boring_hoover". They can be killed using this name:
`docker kill boring_hoover`

`docker run -d -p 8080:80 --name web-server nginx`
`-p 8080:80`: This maps port 8080 on our local machine to port 80 of the container. If we issue an https request on 8080, this is mapped to the container port 80 and we should get a response.
`--name`: This allows us to explicitly name our container process.

We can check this is working by running `curl http://localhost:8080` or by visiting this address in our browser.

`docker stop <name>` will stop a container _gracefully_, whereas `docker kill <name>` will do it _forcefully_.