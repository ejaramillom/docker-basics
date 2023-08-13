# build only containers for react apps

```
# in Dockerfile.prod

FROM node:14-alpine

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

CMD ['npm', 'run', 'build']
```

 to be able to set a server for this container, we need to set a multi stage builds

 # multi stage builds

 - one dockerfile with multiple build steps called stages
 - stages can copy results from each other
 - we use `RUN` instead of `CMD` in multi stage builds

```
# in Dockerfile.prod

FROM node:14-alpine as build # we name the stage whatever we want

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

RUN npm run build

FROM nginx:stable-alpine # this FROM statement creates a new stage

COPY --from=build /app/build /usr/share/nginx/html # the folder build has all the files created for the server

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]


```