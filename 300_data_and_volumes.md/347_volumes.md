# volumes

- are folders on your host machine hard drive, mounted (made available or mapped) into containers
- they are mapped from docker to the machine and viceversa
- changes in one folder will be accessible in the other folder (changes in the machine are reflected in the container) and so on
- volumes persist when a container is shut down
- volume is not removed when container is removed

```
FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

VOLUME [ "/app/feedback" ] # whis allows us to connect the folder in the container with the folder in the machine

CMD [ "node", "server.js" ]
```

- `[ "/app/feedback" ]` is the route inside the container