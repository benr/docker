#
# lighttpd Testing Docker Container
# Syntax Ref: https://docs.docker.com/reference/builder/
#             https://docs.docker.com/articles/dockerfile_best-practices/

FROM ubuntu:12.04
MAINTAINER benr@cuddletech.com

## Each argument of RUN needs to be parsed, do not include in "quotes"
RUN /usr/bin/apt-get update
RUN /usr/bin/apt-get install -y lighttpd

# ADD <src> <dest>	Copy or extract a URL, TAR, or local directory into the container
# COPY <src> <dest>	Simpler and faster, use when just copying files
COPY src/ /var/www/

EXPOSE 80

# CMD		Run a command on start, which can be overridden by the docker command line ('docker run <img> some -other-cmd')
# ENTRYPOINT 	Run a command on start but can not be overriden at start, things passed are treated as arguments ('docker run <img> -arg-to -entrypoint')
##   Use them together to create an entrypoint with default arguments that can be overriden 

ENTRYPOINT ["/usr/sbin/lighttpd","-f","/etc/lighttpd/lighttpd.conf"]
# Pass -D to foreground!
CMD ["-D"]

