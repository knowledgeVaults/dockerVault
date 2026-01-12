# Docker: Docker Image Layers

Image layers are the stacked read-only filesystem layers that make up a Docker image

* Every line in a Dockerfile creates a new immutable read-only layer 
* Each layer only stores the changes of the previous layer
* A layer can only be changed by modifying the Dockerfile and initiating a new build

![](https://raw.githubusercontent.com/knowledgeVaults/imagesVault/main/docker-image-layers.png)

<br>

# Image Layer Properties

* **Immutable**: Can never change once created
* **Cached**: Docker can reuse unchanged layers which helps save disk space 
* **Shared across images**: A single layer built by an image can be reused by different images 
* **Union filesystem**: Docker uses a union filesystem to merge all layers into a single view during runtime 

<br>

# Container Layer

The container layer is the single writable filesystem layer that Docker adds on top of the image layer when a container is created

* Not part of the Docker image
* Exists only for the lifetime of the container
* Provides a temporary writable filesystem so that the container can run, change files, and produce output while keeping the image immutable
* Docker copies the changes into the container layer and is designed for temporary state
