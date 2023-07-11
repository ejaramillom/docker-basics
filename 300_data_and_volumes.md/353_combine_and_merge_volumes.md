# merge

- `docker run -d -p 3000:80 --name feedback-app -v feedback:/app/feedback -v "/Users/teacher/development/teaching/udemy/docker-complete:/app" feedback-node:volumes`

here:

- `-v feedback:/app/feedback` is the route of the anonymous volume (files inside the container)
  
- `feedback-node:volumes` converts the anonymous volume into a named volume
  
- `"/Users/teacher/development/teaching/udemy/docker-complete:/app"` creates a bind mount for the volume, it connects a local folder of our choice to the folder of the container we choose, like `/app` (files outside the container)

- when docker file runs `COPY . .` it copies all the data in the image to the container. this data is saved in `/app` which is a mirror of `/Users.....`
  
- the problem is, the local folder `/Users....` does not contain an installation of the dependencies, because the previous overrides all the files in the container folder `/app`

## create anonymous volumes in the local folder to install the runtime environments



### anonymous volume 

- `-v /app/node_modules`

### named volume

- `-v thing_name:/app/node_modules`