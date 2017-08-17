FROM java:8u91-jdk

MAINTAINER GAMMOUDI NEJI <ngammoudi@exoplatform.com>

ENV JMXTRANS_VERSION 256
RUN echo "debconf debconf/frontend select noninteractive" | debconf-set-selections
RUN wget http://central.maven.org/maven2/org/jmxtrans/jmxtrans/${JMXTRANS_VERSION}/jmxtrans-${JMXTRANS_VERSION}.deb
RUN dpkg -i jmxtrans-${JMXTRANS_VERSION}.deb


ADD run-jmxtrans.sh /usr/bin/run-jmxtrans.sh
COPY exo_jcr.json /var/lib/jmxtrans
COPY tomcat_ds.json /var/lib/jmxtrans
RUN chmod +x /usr/bin/run-jmxtrans.sh

# default json confs dir
VOLUME ["/var/lib/jmxtrans"]

# default logs dir
VOLUME ["/var/log/jmxtrans"]

CMD /usr/bin/run-jmxtrans.sh
