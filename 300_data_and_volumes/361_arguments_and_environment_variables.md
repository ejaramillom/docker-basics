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

# Environment Variables & Security

One important note about environment variables and security: Depending on which kind of data you're storing in your environment variables, you might not want to include the secure data directly in your Dockerfile.

Instead, go for a separate environment variables file which is then only used at runtime (i.e. when you run your container with docker run).

Otherwise, the values are "baked into the image" and everyone can read these values via `docker history <image>`

For some values, this might not matter but for credentials, private keys etc. you definitely want to avoid that!

If you use a separate file, the values are not part of the image since you point at that file when you run docker run. But make sure you don't commit that separate file as part of your source control repository, if you're using source control.