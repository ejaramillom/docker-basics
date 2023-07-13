# container and image building

- `docker build . -t favorites-node` we build the image
- `docker run --name favorites -d --rm -p 2999:3000 favorites-node` keeping it simple for now
- database won't get erased when we delete the container
- this fails when connecting with mongodb (but this is not a problem with http requests)

## containers can send http request out of the box