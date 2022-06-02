# t-rex container
ARG DEB_URL

FROM ubuntu:focal

RUN apt-get update && apt-get install -y curl libssl1.1 gdal-bin
RUN apt-get update && apt-get install -y telnet

RUN curl -o t-rex.deb -L ${DEB_URL} && \
    dpkg -i t-rex.deb && \
    rm t-rex.deb

USER www-data

WORKDIR /var/data/in

VOLUME ["/var/data/in"]
VOLUME ["/var/data/out"]

EXPOSE 6767 3000
ENTRYPOINT ["/usr/bin/t_rex"]
