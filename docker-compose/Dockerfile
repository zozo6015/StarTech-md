FROM nginx:latest
MAINTAINER  "StarTech-RD"
USER root

RUN   apt update

RUN   apt -y upgrade

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
                         sed \
                         curl \
                         gnupg2

RUN   curl -sL https://deb.nodesource.com/setup_8.x | bash - && \
                               apt install -y nodejs


RUN   npm install pm2@latest -g

RUN   mkdir -p /run/php

WORKDIR   /root

ADD   apps.yaml /opt/apps.yaml

EXPOSE 80

CMD   ["/usr/local/bin/pm2", "start", "/opt/apps.yaml", "--no-daemon"]
