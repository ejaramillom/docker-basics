# read only volumes

- by default containers can read and write documents from the file system
- we need to block the container from editing or deleting files
- then we need to run:

```
docker run -d --rm -p 2999:80 --name feedback-app -v feedback:/app/feedback -v "/Users/path/to/thing/for/app:/app:ro" -v /app/node_modules -v /app/temp -v feedback-node:volumes
```

the line `:/app:ro` converts the volume so that the container cannot write the files in that path.