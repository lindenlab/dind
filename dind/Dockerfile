FROM registry.docker/jpetazzo/dbyd
MAINTAINER don@lindenlab.com
    
ADD docker-config-linden_*.deb ./
RUN dpkg -i --force-confdef --force-confold docker-config-linden_*deb && rm docker-config-linden_*.deb

# Install the magic wrapper.
ADD ./wrapdocker /usr/bin/wrapdocker
RUN chmod +x /usr/bin/wrapdocker
CMD ["wrapdocker"]

