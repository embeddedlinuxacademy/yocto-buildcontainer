FROM ubuntu:18.04

# install general tools
RUN apt-get update && \
    DEBIAN_FRONTEND="noninteractive" apt-get install --no-install-recommends -y \
    apt-utils sudo curl git-core gnupg linuxbrew-wrapper locales \
    nodejs zsh wget nano npm fonts-powerline tmux vim

# install yocto tools
RUN DEBIAN_FRONTEND="noninteractive" apt-get install --no-install-recommends -y \
    gawk wget git-core diffstat unzip texinfo gcc-multilib \
    build-essential chrpath socat cpio python3 python3-pip python3-pexpect \
    xz-utils debianutils iputils-ping python3-git python3-jinja2 \
    libegl1-mesa libsdl1.2-dev pylint3 iproute2 file iptables

# set up locale
RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8

# add a user
RUN useradd -ms /bin/zsh dev && echo "dev:docker" | chpasswd && adduser dev sudo
USER dev

# run zsh installation script
RUN sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# set workdir
WORKDIR /home/dev/workspace

# start zsh
ENTRYPOINT [ "/bin/zsh" ]

