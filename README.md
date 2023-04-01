# anthony.portainer.io

Static content for anthony.portainer.io

# Install Docker + Portainer

Valid for Ubuntu 22.04

```
curl https://anthony.portainer.io/docker | sudo bash
```

# LXD images build

Create a builder LXC container first:

```
lxc launch ubuntu:22.04 lxd-image-builder -c security.nesting=true
lxc exec lxd-image-builder bash
```

## flask-docker


```
lxd init --minimal
lxc remote add --protocol simplestreams ubuntu-minimal https://cloud-images.ubuntu.com/minimal/releases/
lxc launch ubuntu-minimal:22.04 flask-docker-ub-2204-min
lxc exec flask-docker-ub-2204-min -- bash -c "curl https://anthony.portainer.io/lxd/image-build-flask-docker-ub-2204-min | bash"
lxc stop flask-docker-ub-2204-min
lxc publish flask-docker-ub-2204-min --alias flask-docker
lxc image export flask-docker flask-docker-ub-2204-min
```