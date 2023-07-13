# containers communication

- we pull the docker image from docker hub
- `docker run -d --name mongodb mongo` mongo is the image we will start
- but then 'mongodb://host.docker.internal.....' won't work anymore
- we write then `docker container inspect mongodb` and copy the address of the container to copy it in the code

"NetworkSettings"
  "IPAddress": 65165161 #  we need to copy this IP Address and put it in the code

- the code in the app will be `mongoose.connect('mongodb://65165161.27017/swfavorites')`
- then the containers can communicate

