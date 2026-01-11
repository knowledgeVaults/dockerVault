# Docker: Image Layers

Image layers are the stacked read-only filesystem layers that make up a Docker image

* Every line in a Dockerfile creates a new immutable read-only layer
* Each layer only stores the changes of the previous layer
* A layer can only be changed by modifying the Dockerfile and initiating a new build

![docker-image-layers-diagram](https://github.com/knowledgeVaults/imagesVault/blob/main/docker-image-layers.png)

<br>

# Image Layer Properties

* **Immutable**: Can never change once created
* **Cached**: Docker can reuse unchanged layers which helps save disk space 
* **Shared across images**: A single layer built by an image can be reused by different images 
* **Union filesystem**: Docker uses a union filesystem to merge all layers into a single view during runtime 