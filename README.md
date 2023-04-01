# anthony.portainer.io

Static content for anthony.portainer.io

# Install Docker + Portainer

Valid for Ubuntu 22.04

```
curl https://anthony.portainer.io/docker | sudo bash
```

# LXD images build

## flask-docker

```
lxc launch ubuntu-minimal:22.04 base-flask-min
lxc exec base-flask-min "curl https://anthony.portainer.io/lxd/image-build-flask-docker-ub-2204-min | bash"
```