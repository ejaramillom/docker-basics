# merge

- `docker run -d -p 3000:80 --name feedback-app -v feedback:/app/feedback -v "/Users/teacher/development/teaching/udemy/docker-complete:/app" feedback-node:volumes`

here:

- `-v feedback:/app/feedback` is the route of the anonymous volume (files inside the container)
  
- `feedback-node:volumes` converts the anonymous volume into a named volume
  
- `"/Users/teacher/development/teaching/udemy/docker-complete:/app"` creates a bind mount for the volume, it connects a local folder of our choice to the folder of the container we choose, like `/app` (files outside the container)

- when docker file runs `COPY . .` it copies all the data in the image to the container. this data is saved in `/app` which is a mirror of `/Users.....`
  
- the problem is, the local folder `/Users....` does not contain an installation of the dependencies, because the previous overrides all the files in the container folder `/app`

## create anonymous volumes in the local folder to install the runtime environments

- when we assign the `/Users...` route to `/app` route we are overwriting everything in that folder of the container when whe `COPY` the content, but when we assign a new anonymous volume `/app/node_modules` it survives because the longest route assignemnt has priority for docker, so it survives and keeps the folder created with the command `RUN npm install` in the docker file

### anonymous volume 

- `-v /app/node_modules`

### named volume

- `-v thing_name:/app/node_modules`