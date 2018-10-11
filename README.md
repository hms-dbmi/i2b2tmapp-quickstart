# i2b2/tranSMART release-18.1 Quick-Start 
## Application Stack Only


## Docker Host Hardware Requirements

-   8GB RAM
-   64GB of free Hard Drive space
-   [Docker for Mac](https://docs.docker.com/docker-for-mac) and [Docker for Windows](https://docs.docker.com/docker-for-windows/) are not supported unless you use docker-machine to create a VM that meets the requirements for RAM and Hard Drive space.

## Docker Network Requirements

-   HTTP (80) and HTTPS (443) ports (default)
-   Edit `.env` file to assign different ports

```bash
HTTP_PORT=
HTTPS_PORT=
```

## Compatible Docker Versions

    Docker: 17.06.2+
    docker-compose: 1.14.0+

## Deploy

```
$ docker-compose up -d
```

## Test i2b2/tranSMART release-18.1

1.  Browse to your docker machine IP
2.  i2b2/tranSMART, by default, uses self-signed certificates. If the browser complains about security, 'click OK' to allow for security exception.
3.  Default username and passwords are used, e.g. admin/admin

## Open discussion forum
https://discuss.i2b2transmart.org

## Docker-machine installation - MAC/Windows
https://tinyurl.com/docker-VM
