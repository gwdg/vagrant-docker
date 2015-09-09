FROM ubuntu:trusty

MAINTAINER Maik Srba <maik.srba@gwgd.de>

RUN \
  apt-get update && \
  apt-get -y install \
          apache2 && \
  rm /var/www/html/index.html && \
  rm -rf /var/lib/apt/lists/*

COPY setup/files/httpd-foreground /usr/local/bin/

EXPOSE 80
CMD ["httpd-foreground"]