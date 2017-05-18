FROM fedora:25
MAINTAINER Greg Orzell <chaos@chaossystems.io>

ENV HOME /rpm-build
WORKDIR ${HOME}

# Install base packages
RUN dnf makecache && \
    dnf install -y \
    # Circle CI Requirements
    git ssh gzip ca-certificates \
    # RPM Tools and CLI depdencencies
    curl python-devel python-pip make rpm-build createrepo && \
    dnf clean all

# Install AWS/ECS CLI Tools
RUN pip install --upgrade pip && \
    pip install setuptools && \
    pip install awscli

CMD ["/bin/bash"]
