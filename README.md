This repository contains configuration files for building a 
[Docker](https://docker.com/) image for the Madsonic media streamer.

[![](https://imagelayers.io/badge/mbirth/madsonic:latest.svg)](https://imagelayers.io/?images=mbirth/madsonic:latest 'Get your own badge on imagelayers.io')
[![](https://images.microbadger.com/badges/image/mbirth/madsonic.svg)](http://microbadger.com/#/images/mbirth/madsonic "Get your own image badge on microbadger.com")


Noteworthy
----------

* [Madsonic 6.2 Beta](http://www.madsonic.org/)
* based on [cyrilix](https://github.com/cyrilix)/[docker-subsonic](https://github.com/cyrilix/docker-subsonic)
* uses [jeanblanchard](https://github.com/jeanblanchard)/[tomcat](https://hub.docker.com/r/jeanblanchard/tomcat/) with Alpine Linux
* compiles to a 262 MB image


Volumes
-------

* `/data` --- Directory to store Madsonic's log, configuration and database
* `/music` --- Default music folder
* `/podcasts` --- Default podcast folder
* `/playlists` --- Default playlist folder


Environment Variables
---------------------

* `TZ` --- timezone setting, default: `Europe/Berlin`
* `MAX_MEM` --- maximum Java heap size in megabytes, default: `256`


Build your own image
--------------------

```shell
$ docker build -t <your-name>/docker-madsonic .
```


Get a pre-built image
---------------------

A current image is available as a trusted build from the Docker index:

```shell
$ docker pull mbirth/madsonic
```

The repository page is at
https://hub.docker.com/r/mbirth/madsonic/


Run a container with this image
-------------------------------

```shell
$ docker run \
  --detach \
  --publish 4040:4040 \
  --volume "/wherever/your/music/is:/music/:ro" \
  <your-name>/madsonic

```
