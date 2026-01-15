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
* All changes made to the base image are copied and stored into this layer using the **Copy-on-Write** method
* Designed for temporary state and to provide a temporary filesystem
 
<br>

## Copy-on-Write

CoW is a storage optimization technique Docker uses where Docker will copy a file into the container layer before modifying it