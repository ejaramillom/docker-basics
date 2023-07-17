# react docker apps

```
FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 3000

CMD ["npm", "start"]
```

then we can tag the build for the image

- `docker build -t goals-react .`

after that we can run a container

- `docker run --name goals-react --rm -d -p 3000:3000 -it goals-react`

we need it to start in interactive mode, so that the container works correctly