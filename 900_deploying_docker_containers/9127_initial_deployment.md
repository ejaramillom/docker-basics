# deployment

- first we build the image
- `docker build -t node-dep-example .`
- `docker run -d --rm --name node-dep -p 80:80 node-dep-example`
- no networks or volumes for this one
