# updating remote container

- to update the code in the remote container we rebuild the image locally
- `docker build -t node-dep-example-1 .`
- then retag the container
- `docker tag node-dep-example-1 academind/node-example-1`
- then push again the image to docker hub
- `docker push academind/node-example-1`

## on AWS

- her we have to go to `AWS clusters > default`
- go to `tasks`
- then go to `task definition` link on the list of tasks that are running, in this case the currently running task with the app that was deployed
- `create new revision`
- leave the settings that were already selected the first time
- then `actions`
- then `update service`
- `skip to review`
- `update service`
- then we wait for it to finish running the task, and then we search for the IP to connect