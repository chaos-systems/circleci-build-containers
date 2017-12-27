ARG FROM_TAG=17.10

FROM ubuntu:$FROM_TAG
MAINTAINER Greg Orzell <chaos@chaossystems.io>

ENV HOME /deb-build
WORKDIR ${HOME}

# Install base packages
RUN apt-get update && \
    apt-get install --no-install-recommends -y \
    apt-transport-https \
    build-essential \
    curl \
    debootstrap \
    debhelper \
    dpkg-dev \
    devscripts \
    germinate \
    make \
    reprepro \
    software-properties-common \
    # Circle CI Requirements
    ca-certificates \
    git \
    gzip \
    ssh

# Install S3 repo tools
RUN apt-get install --no-install-recommends -y \
    ruby && \
    gem install deb-s3 && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists

CMD ["/bin/bash"]
