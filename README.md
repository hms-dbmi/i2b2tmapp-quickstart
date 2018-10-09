# i2b2/tranSMART release-18.1 Quick-Start ( Application Stack Only) 


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
$ docker-compose -f prod.yml down -v
```

## Test i2b2/tranSMART release-18.1

1.  Browse to your docker machine IP
2.  i2b2/tranSMART, by default, uses self-signed certificates. If the browser complains about security, 'click OK' to allow for security exception.
3.  Default username and passwords are used, e.g. admin/admin

## Troubleshoot

Biggest point of failure is deploying the database for the first time. Due to its size and resource requirements, your Docker client may timeout during first deployment of the database.

Docker is transferring the data from the Docker database image to the named volume `quickstart_i2b2transmart-db`. Notice, by running `docker system df` the total volume size increase:

```bash
TYPE          TOTAL         ACTIVE        SIZE          RECLAIMABLE
Local Volumes 11            2             25.24GB       25.24GB (100%)
```

If you run into a timeout error:

```bash
ERROR: for quickstart_db_1  HTTPSConnectionPool(host='xxxx', port=2376): Read timed out. (read timeout=60)
```

Wait for data transfer to complete and the client to re-sync with the docker machine (~100s). Resume the deployment by running `docker-compose up -d db` again.

## Open discussion forum
https://discuss.i2b2transmart.org

## Docker-machine installation - MAC/Windows
https://tinyurl.com/docker-VM
