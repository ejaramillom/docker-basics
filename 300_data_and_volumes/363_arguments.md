# arguments

- we can put magic numbers and values with arguments

```
FROM node:14

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

ARG DEFAULT_PORT = 80

ENV PORT = $DEFAULT_PORT

EXPOSE $PORT

CMD [ "npm", "start" ]
```

- we can build the image with this dockerfile, but we also can specify other arg values in the build command like this:

- `docker build . -t feedback-app:work-test --build-arg DEFAULT_PORT=8000 `