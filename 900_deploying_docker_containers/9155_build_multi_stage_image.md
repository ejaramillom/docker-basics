# publishing a multi stage image

- `docker build -f frontend/Dockerfile.prod academind/goals-react -t ./frontend`  # this is the production ready image
- `docker push academind/goals-react`