# image layers

- only the instructions that changed are rebuilt, and the ones after it
- docker understands that it does not have to re run every instruction if no changes are made (layer-based-architecture)

```
FROM node

WORKDIR /app

COPY package.json /app # this would improve performance

RUN npm install

COPY . /app

EXPOSE 80 

CMD ["node", "server.js"]
```

by adding the line of `COPY Package.json` we are improving performance of the docker file, because we wont run npm install every time we change a file in the project, only when we add new node packages or libraries to the repo.