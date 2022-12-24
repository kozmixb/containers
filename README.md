# Containers Library

Applications containerized and ready to launch.

## Get an image

The recommended way to get any of the Images is to pull the prebuilt image from the [Docker Hub Registry](https://hub.docker.com/r/bencejoob/).

```console
$ docker pull bencejoob/APP
```

To use a specific version, you can pull a versioned tag.

```console
$ docker pull bitnami/APP:[TAG]
```

If you wish, you can also build the image yourself by cloning the repository, changing to the directory containing the Dockerfile and executing the `docker build` command.

```console
$ git clone https://github.com/kozmixb/containers.git
$ cd APP
$ docker build -t bencejoob/APP .
```

> Remember to replace the `APP` placeholders in the example command above with the correct values.