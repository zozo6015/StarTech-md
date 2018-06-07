FROM debian:9
MAINTAINER  "Keresztes Péter-Zoltán"
USER root

RUN   apt update

RUN   apt -y install php7.0 \
                         php7.0-bcmath \
                         php7.0-bz \
                         php7.0-cli \
                         php7.0-common \
                         php7.0-curl \
                         php7.0-fpm \
                         php7.0-gd \
                         php7.0-mbstring \
                         php7.0-mcrypt \
                         php7.0-mysql \
                         php7.0-readline \
                         php7.0-soap \
                         php7.0-tidy \
                         php7.0-xml \
                         php7.0-xmlrpc \
                         php7.0-zip \
                         sed

RUN   mkdir -p /run/php

RUN   sed -i 's/listen.*/listen\ =\ 0.0.0.0:9000/' /etc/php/7.0/fpm/pool.d/www.conf \
      sed -i 's/log_level.*/log_level\ =\ debug/' /etc/php/7.0/fpm/php-fpm.conf

WORKDIR   /root

CMD   ["/usr/sbin/php-fpm7.0", "-c", "/etc/php/7.0/fpm/php.ini", "-y", "/etc/php/7.0/fpm/php-fpm.conf", "-F"]
