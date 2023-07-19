# utility container input

- `docker run -it -d node` # a detached node container
- `docker exec vigorous_dewney npm init` # then we will have to follow a set of steps to create a new project inside the container
- `docker stop vigorous_dewney`
- `docker run node -it node npm init`

## dockerfile

lets create a dockerfile for the utility container

```
FROM Node:14-alpine

WORKDIR /app 
```

- then we will build the image only with this
- `docker build . -t node-util`
- `docker run -it -v /User/teacher/udemy/docker-complete:/app node-util npm init`
- then the files are created in the bind mount