# copy or remove files

- lets say we created new files in the repository or folder like: dummy/text.txt
- then we created a container `docker run ...`
- `docker cp dummy/. thing_name:/app` will add the files inside the folder to the container thing_name in the folder app

## how can we check the new files

- delete the local file
- `docker cp thing_name:/app dummy` will copy the file from the container to the local folder

