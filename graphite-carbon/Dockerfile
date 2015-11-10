FROM ubuntu:trusty

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get -y update
RUN apt-get -y install graphite-carbon

COPY carbon.conf /etc/carbon/carbon.conf
COPY storage-schemas.conf /etc/carbon/storage-schemas.conf
COPY graphite-carbon /etc/default/graphite-carbon

EXPOSE 2003
VOLUME /var/lib/graphite/whisper/

CMD service carbon-cache start && tail -f /var/log/carbon/console.log