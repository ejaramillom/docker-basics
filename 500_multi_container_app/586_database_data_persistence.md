# volumes

we can find the volume name to persist the data in hub.docker.com/mongo

- `docker run --name mongodb -v data:/data/db --rm -d --network goals-net mongo`

for db credentials we should re run the container

- `docker run --name mongodb -v data:/data/db --rm -d --network goals-net -e MONGO_INITDB_ROOT_USERNAME=name_user MONGO_INITDB_ROOT_PASSWORD=secret mongo`

so that we pass user and password to the database connection, like this:

- `mongodb://max:secret@mongodb:27017/course-goals/?authSource=admin`

we should replace those hardcoded values into environment variables

