FROM node:7
MAINTAINER Greg Orzell <chaos@chaossystems.io>

RUN apt-get update &&\
    apt-get install --no-install-recommends -y apt-transport-https curl software-properties-common make \
    # Circle CI Requirements
    git openssh gzip ca-certificates &&\
    # Setup docker repo and install docker.
    curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add - &&\
    add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable" &&\
    apt-get update &&\
    apt-get install --no-install-recommends -y docker-ce python-dev python-pip &&\
    pip install docker-compose &&\
    apt-get autoremove -y python-pip python-dev &&\
    apt-get clean && \
    rm -rf /var/lib/apt/lists

CMD ["/bin/bash"]
