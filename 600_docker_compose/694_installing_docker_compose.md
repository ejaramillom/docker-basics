# installation

On macOS and Windows, you should already have Docker Compose installed - it's set up together with Docker there.

On Linux machines, you need to install it separately.

These steps should get you there:

1. `sudo curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`

2. `sudo chmod +x /usr/local/bin/docker-compose`

3. `sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose`

4. to verify: `docker-compose --version`