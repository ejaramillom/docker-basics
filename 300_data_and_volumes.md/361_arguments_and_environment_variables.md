# arguments

- ARG
- ARGs run during build time
- variables that can be used inside docker file, but not accessible in console or any application code
- they are set on docker build with `--build-arg`

# environment variables

- ENV
- ENVs run during runtime
- available in dockerfile and inside the application
- they are set using `--env`

## example

```
app.listen(process.env.PORT)

# in dockerfile

ENV PORT 80

EXPOSE $PORT
```

so, we can use the PORT env and expose it in the app built in the container
here we are no longer using a hardcoded value for the port, 
we can define it during runtime (we don't have to rebuild the container)

- `docker run -d --rm -p 3000:8000 --env (or -e) PORT=8000 --name feedback-app -v ....`

we can specify the port as ENV in the runtime command

## .env files

- we can create a file in the root foolder and name it whatever we want and then call it in runtime, like this:

- `./.env` (we named the file .env)
- `docker run -d --rm -p 3000:8000 --env-file ./.env --name feedback-app -v ....`