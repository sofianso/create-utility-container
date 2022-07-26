# Purpose
The purpose of utility container is to run the application without installing any dependencies on the host machine.

## Build the image
```bash
docker build -t mynpm .
```

## Run the image
The following creates package.json file in the host machine using the image created above.
```bash
docker run -it -v /Users/sofian.so/Udemy/create-utility-container:/app node-util npm init
```

## Restrict NPM from being overwritten
```bash
docker run -it -v /Users/sofian.so/Udemy/create-utility-container:/app node-util npm install
```

## ENTRYPOINT
Command inside `ENTRYPOINT` is appended to the docker run command

## Run the image with ENTRYPOINT
The volume will bind any packages installed/removed back to the host machine.
```bash
docker run -it -v /Users/sofian.so/Udemy/create-utility-container:/app mynpm npm init
```

## Install package.json in the Docker image with ENTRYPOINT
```bash
docker run -it -v /Users/sofian.so/Udemy/create-utility-container:/app mynpm npm install 
```

## [EXAMPLE] Install EXPRESS package in the image with ENTRYPOINT
```bash
docker run -it -v /Users/sofian.so/Udemy/create-utility-container:/app mynpm npm install express
```

Run A Single Service from docker-compose
1. `npm` is one of the services listed in `docker-compose.yaml` file
2. `--rm` removes any stopped containers automatically.
```bash
docker-compose run --rm npm init
```
