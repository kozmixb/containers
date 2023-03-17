# Containers Library

Applications containerized and ready to launch.

## Get an image

The recommended way to get any of the Images is to pull the prebuilt image from the [Docker Hub Registry](https://hub.docker.com/r/bencejob/).

```console
$ docker pull bencejob/APP
```

To use a specific version, you can pull a versioned tag.

```console
$ docker pull bencejob/APP:[TAG]
```

If you wish, you can also build the image yourself by cloning the repository, changing to the directory containing the Dockerfile and executing the `docker build` command.

```console
$ git clone https://github.com/kozmixb/containers.git
$ cd APP
$ docker build -t bencejob/APP .
```

> Remember to replace the `APP` placeholders in the example command above with the correct values.

## Build images for multi platform environments

```
docker buildx create --use
docker buildx build -t bencejob/*** --platform linux/x86_64,linux/arm64 --push ./***
```