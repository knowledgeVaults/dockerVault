# Docker: Volumes

<br>

# Mounting

## Volume Mounting

* Mounts any volume from the `var/lib/docker/volumes` directory

Create volume (Optional since Docker will automatically create and mount the volume onto the container if you directly try to mount the volume)
```Bash
docker volume create VOLUME_NAME
```

<br>

Mount volume
```Bash
docker run -v VOLUME_NAME:/var/lib/mysql mysql
```

<br>

## Bind Mounting

* Mounts any volume from any location on the Docker host

```Bash
docker run -v VOLUME_PATH:/var/lib/mysql mysql
```