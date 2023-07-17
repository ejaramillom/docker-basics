# dockerfile for node app

```
FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

CMD ["node", "app.js"]
```

then we build an image:

- `docker image prune -a`
- `docker build -t goals-node .`
- `docker run --name goals-backend --rm goals_node`
- then fix the URL
- `mongodb://host.docker.internal:27017/course-goals`
- then rerun the container
- then expose and publish the ports
- `docker run --name goals-backend --rm -d -p 80:80 goals-node`
