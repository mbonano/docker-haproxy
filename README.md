## Docker HAProxy Project

This repository contains the corrected **Dockerfile** for [Haproxy](http://haproxy.1wt.eu/) and is a modification of two seperate repositories, https://github.com/dockerfile/haproxy and https://github.com/docker-library/haproxy.

This Dockerfile has been published to the public [Docker Hub Registry](https://registry.hub.docker.com/).

### Usage

    $ docker run -d -it -p 80:80 --name haproxy mbonano/docker-haproxy

#### Customizing Haproxy

    $ docker run -d -it -v <override-dir>:/haproxy-override -p 80:80 --name haproxy mbonano/docker-haproxy

where `<override-dir>` is an absolute path of a directory that could contain:

  - `haproxy.cfg`: custom config file (replace `/dev/log` with `127.0.0.1`, and comment out `daemon`)
  - `errors/`: custom error responses

After few seconds, open `http://<host>/haproxyStats` to see the haproxy stats page.