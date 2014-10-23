FROM registry.docker/debian:jessie
MAINTAINER don@lindenlab.com

# Let's start with some basic stuff.
RUN apt-get update -qq && apt-get install -qqy \
    apt-transport-https \
    ca-certificates \
    curl \
    lxc \
    iptables
    
# Install Docker from Linden repositories.
ADD ./docker.list /etc/apt/sources.list.d/docker.list
RUN apt-get update -qq && apt-get install -o Dpkg::Options::="--force-confdef" -o Dpkg::Options::="--force-confold" -qqy --allow-unauthenticated docker-config-linden && apt-get clean

# Install the magic wrapper.
ADD ./wrapdocker /usr/bin/wrapdocker
RUN chmod +x /usr/bin/wrapdocker

# Define additional metadata for our image.
VOLUME /var/lib/docker
CMD ["wrapdocker"]

