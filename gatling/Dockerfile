
FROM ubuntu:15.04

MAINTAINER GAMMOUDI NEJI <ngammoudi@exoplatform.com>
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y  software-properties-common && \
    add-apt-repository ppa:webupd8team/java -y && \
    apt-get update && \
    echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections && \
    apt-get install -y oracle-java7-installer && \
    apt-get clean

ADD /gatling.zip /var/gatling.zip
RUN mkdir -p /var/gatling
RUN cd /var
RUN unzip  /var/gatling.zip -d /var/gatling
RUN rm -rf gatling.zip

CMD ["bash"]