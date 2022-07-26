# Purpose
The purpose of utility container is to run the application without installing any dependencies on the host machine.

## Build the image
```bash
docker build -t node-util .
```

## Run the image
The following creates package.json file in the host machine using the image created above.
```bash
docker run -it -v /Users/sofian.so/Udemy/create-utility-container:/app node-util npm init
```
