# py-k8s-runtime
This project wants to implement a pythonic way to bring your application into your cluster without the need of any specialized knowledge.

## Status

design and conception phase

## Description

With this library, you can write your Dockerfile and Kubernetes-Configuration-Files within your python application.

In the example.md file, you can find a first example to use this library. Currently it is under a conception phase.


## Usage

This library adds a new module named "microservice" with the class "microservice", which takes a docker and k8s client.

## Hub for container images

If you want to use kubernetes, you need a hub for your container images to take from. You can configure the hub in your docker client.

The kubernetes client will be configured to take the image from your hub, where the library will push the image to.

## Linklist

- [Docker-py build](https://docker-py.readthedocs.io/en/stable/images.html#docker.models.images.ImageCollection.build)
  - takes fileobj (should be a dockerfile-file)
