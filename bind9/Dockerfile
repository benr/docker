#

FROM ubuntu:14.04
MAINTAINER benr@cuddletech.com

## Each argument of RUN needs to be parsed, do not include in "quotes"
RUN /usr/bin/apt-get update
RUN /usr/bin/apt-get install -y bind9 dnsutils

VOLUME /etc/bind
COPY db/ /etc/bind/

EXPOSE 53
EXPOSE 53/udp

ENTRYPOINT ["/usr/sbin/named","-fg","-u","bind"]

