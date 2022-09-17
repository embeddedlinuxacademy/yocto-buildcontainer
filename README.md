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
* [kas](https://github.com/siemens/kas)


## Getting Started

To start the development container use the following commands.

### Startup of the development environment

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

### Run simple bitbake command
* Clone poky (and other layers)
    ```
    git clone --branch <yocto-version> git://git.yoctoproject.org/poky
    ```
* Source build environment
    ```
    source poky/oe-init-build-env
    ```
* [Optional] Adapt configuration
  * Add additional layers to bblayers.conf
  * Add configuration to local.conf

* Start build
    ```
    bitbake <image-name>
    ```

#### Use kas configuration
* [Optional] Adapt default kas configuration in workspace/.config.yaml
* Start build
    ```
    kas build
    ```
* [Optional] Attach to bitbake shell to run single bitbake commands
    ```
    kas shell
    ```
  or to use the bash instead of sh
    ```
    kas shell -c /bin/bash
    ```
