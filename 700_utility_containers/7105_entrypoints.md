# entrypoints

- `docker run -it -v /User/teacher/udemy/docker-complete:/app node-util npm install`
- we should restrict the actions we can do from the docker container
  
```
FROM Node:14-alpine

WORKDIR /app 

ENTRYPOINT [ "npm" ]
```

the entrypoint allows us to prepend commands after the word `npm` so we can send additional actions to execute in the container run

- `docker run -it -v /User/teacher/udemy/docker-complete:/app my-app init` # then it shuts down
- `docker run -it -v /User/teacher/udemy/docker-complete:/app my-app install` # then after the shutting down it persist the files in the bind mount
- `docker run -it -v /User/teacher/udemy/docker-complete:/app my-app install express --save` # we can continue running commands to install dependencies
