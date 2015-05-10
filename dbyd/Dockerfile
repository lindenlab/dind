FROM registry.docker/debian:jessie
MAINTAINER don@lindenlab.com

# Install Docker from Linden repositories.
ADD ./docker.list /etc/apt/sources.list.d/docker.list
RUN apt-get update -qq
RUN apt-get install -qqy --allow-unauthenticated docker.io

# Define additional metadata for our image.
VOLUME /var/lib/docker

