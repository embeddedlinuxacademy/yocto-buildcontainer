FROM ubuntu:18.04

# install the tools
RUN apt-get update && \
  apt-get install -y sudo curl git-core gnupg linuxbrew-wrapper locales \
  nodejs zsh wget nano npm fonts-powerline tmux vim

# install yocto tools
RUN DEBIAN_FRONTEND="noninteractive" apt-get install -y gawk wget git-core diffstat unzip texinfo gcc-multilib \
    build-essential chrpath socat cpio python3 python3-pip python3-pexpect \
    xz-utils debianutils iputils-ping python3-git python3-jinja2 \
    libegl1-mesa libsdl1.2-dev pylint3 xterm

# set up locale
RUN locale-gen en_US.UTF-8
ENV LANG en_US.UTF-8

# add a user
RUN useradd -ms /bin/zsh dev && echo "dev:docker" | chpasswd && adduser dev sudo
USER dev

# terminal colors with xterm
ENV TERM xterm

# set the zsh theme
ENV ZSH_THEME agnoster

# run the installation script  
RUN wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh || true

# set workdir
WORKDIR /home/dev/workspace

# start zsh
ENTRYPOINT [ "/bin/zsh" ]

