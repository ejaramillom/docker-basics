# pushing updated containers to production

- we make a change in the code
- `docker build -t node-dep-example-1 .` # we rebuild the image
- `docker tag node-dep-example-1 academind/node-example-1`
- `docker push academind/node-example-1` # we push the image to dockerhub
- it only pushes the changes to the remote docker hub image
- then in the remote machine:
- `sudo docker ps`
- `sudo docker stop thing_in_remote`
- `sudo docker run -d --rm -p 80:80 academind/node-example-1`

this did not work because it uses the local docker container it previously had

- we have to re pull the image
- `docker pull node-example-1`
- and then re run the container
- then it works

# shutting down the server

- `sudo docker stop thing_in_remote`
- then in the instances of aws play `actions - instance type - terminate`