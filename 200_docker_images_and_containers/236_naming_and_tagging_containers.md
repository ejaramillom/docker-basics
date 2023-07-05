# names

- are for containers
- `docker run -p 2999:80 -d --rm --name goalsApp 2892342` will add a name to the container when running, the `--name` tag

# tags

- are for images
- they consist of two parts: name : tag
- name: set the general name of the image
- tag: define a specialized version of the image, maybe for a group of images

example:

- `FROM node:14.9.0-stretch` after the colon we added `14.9.0-stretch` from docker hub

- `docker build -t goals:latest .` to create the image with a tag

to remove tagged images:

- `docker image prune -a`