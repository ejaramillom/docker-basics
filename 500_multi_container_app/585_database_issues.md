# database credentials

After running the mongo container with the `MONGO_INITDB_ROOT_USERNAME` and `MONGO_INITDB_ROOT_PASSWORD` flags set and changing the connection string in `backend/app.js` to reflect the `username/password`, I am no longer able to connect to MongoDb. I have rebuilt the backend image and container as well, of course.

I've checked this command over that creates the Mongo container with auth, but still can't figure out what I'm doing wrong:

`docker run --name mongodb -v data:/data/db  --rm -d --network goals-net -e MONGO_INITDB_ROOT_USERNAME=josh -e MONGO_INITDB_ROOT_PASSWORD=secret mongo`

Connection string I'm using in app.js: `mongodb://josh:secret@mongodb:27017/course-goals?authSource=admin`

The following is the error I get when running `docker run --name goals-backend --rm -p 80:80 --network goals-net goals-node`

The problem could be the volume and the fact that you created another user with different credentials before you changed them. Because of the volume, your database is still there and hence your old root user is still set up - i.e. your old credentials apply.

Also see this thread: https://www.udemy.com/course/docker-kubernetes-the-practical-guide/learn/#questions/13015136/

Hence you might want to clear the volume (find it with `docker volume ls`, remove with `docker volume rm`) and then retry.