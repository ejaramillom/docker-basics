# docker

## container

- is a running unit of software

## image

- has the templates and blueprints of the container
- includes the code and the required tools or dependencies in the runtime for the app to work
- one image can create multiple containers based on that image

image => container 1
      => container 2
      => container 3

## docker hub

you can find prebuilt images to run

```
docker pull node
docker run node
docker ps -a // docker processes all
docker run -it node // docker interactive node shell
```


