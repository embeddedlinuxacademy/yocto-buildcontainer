## About The Project

This project contains a development container to build images with the yocto
project.
It uses a Ubuntu 20.04 image as a base and additional tools for the
development environment like zsh.
The user for the image is *dev* with password *docker*.

### Links

* [Docker](https://docker.com)
* [Docker-Compose](https://github.com/docker/compose)
* [zsh + ohmyzsh](https://github.com/ohmyzsh/ohmyzsh)
* [yocto](https://yoctoproject.org)


## Getting Started

To start the development container use the following commands.

### Usage

* Clone repository
     ```
    git clone https://github.com/embeddedlinuxacademy/yocto-buildcontainer
    ```

* Change to cloned folder
    ```
    cd yocto-buildcontainer
    ```

* Run container
    ```
    docker-compose run dev-env 
    ```

* Clone poky
    ```
    git clone --branch <yocto-version> git://git.yoctoproject.org/poky
    ```

* Source build environment
    ```
    source poky/oe-init-build-env
    ```

* Start build
    ```
    bitbake <image-name>
    ```

