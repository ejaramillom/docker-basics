# copy

- when we run the container in production, we need the `COPY` command in the docker file
- the bind mounts are useful during development, so it is necessary to keep them for the local environment and passing the instruction locally

# avoid copying everything

- we should use `dockerignore`
- here is a possible content

```
/.dockerignore
  node_modules
```

we write a dockerignore like this to avoid copying everything

You can add more "to-be-ignored" files and folders to your .dockerignore file.

For example, consider adding the following to entries:

```
    Dockerfile
    .git
```

This would ignore the Dockerfile itself as well as a potentially existing .git folder (if you are using Git in your project).

In general, you want to add anything which isn't required by your application to execute correctly.