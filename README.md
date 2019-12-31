# NGINX Proxy

Most of the hard work in this container is all thanks https://github.com/jwilder/nginx-proxy.

What this adds on top is a SSH server and some extra reading of the docker containers to allow you to connect to your MySQL, Redis...etc servers from the SSH container.

## Instructions

Run:
```
$ docker run -d -p 80:80 2020:22 -v /var/run/docker.sock:/tmp/docker.sock:ro boxednorman/nginx-proxy
```

To SSH into the container run:

```
$ ssh root@localhost -p2020
```

The password is: `root`.

Then using your preferred database manager you should be able to connect to the host of whatever you set the `VIRTUAL_HOST` environment variable to be.