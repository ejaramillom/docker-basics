# images 

## preexisting images

- docker hub

## custom images

- write a dockerfile
- the following is a template, we should not run any server on the image, it is not an instance, is a blueprint of the instance

```
FROM node # we want to start from a local or remote image named node

WORKDIR /app # we set this so that the 'installs' happen here, not in the outside

COPY . /app # dot (.) is the path outside of the image, and the (/app) is the location inside the image

RUN npm install # by default these will be run in the working directory (/app)

EXPOSE 80 # the port where the app will be exposed to the user

CMD ["node", "server.js"] # this won't be executed when the image is created, but when a container is instantiated

```

then we can build the image

```
docker build .
docker run -p 2999:80 'name_of_the_thing' # --publish in the port 3000 the functionality of the image in port 80
docker stop 'name_of_the_thing' # this in another console
```