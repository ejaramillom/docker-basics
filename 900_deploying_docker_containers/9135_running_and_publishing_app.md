# publish an image to be used live

- connect to the remote machine
- `docker run -d --rm -p 80:80 academind/node-example-1`
- with permissions error we should use sudo
- `sudo docker run -d --rm -p 80:80 academind/node-example-1`
- then go to the running instances of AWS
- copy the IPv4 public IP `18.218.126.91`
- by default the instances are disconnected from the WWWd except you using SSH
- then we have to go to the security groups
- on the inbound/outbound rules, the outbound rules everything is permitted, in the inbound rules we define what requests can be managed by the instance
- `edit inbound rules`
- `add rule`
- `source: anywhere`
- `http` rule
- enter a port 80
- then save