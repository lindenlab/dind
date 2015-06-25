FROM registry.docker/debian:jessie
MAINTAINER don@lindenlab.com

RUN apt-get update -qq && apt-get install -qqy \
    apt-transport-https \
    ca-certificates \
    curl \
    lxc \
    perl \
	libapparmor1 \
	libdevmapper1.02.1 \
    iptables

ADD docker.io_*.deb ./
RUN dpkg -i docker.io_*deb && rm docker.io_*.deb

# Define additional metadata for our image.
VOLUME /var/lib/docker

