FROM orsolin/docker-php-5.3-apache

RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y libcurl4-gnutls-dev libpng-dev unzip cron re2c php5-imap python curl php5-curl php5-gd php5-mysql libc-client-dev libkrb5-dev && rm -r /var/lib/apt/lists/*

COPY config/php_extensions/*.ini /etc/php5/apache2/conf.d/

## RUN php5enmod zip

RUN docker-php-ext-configure imap --with-imap-ssl --with-kerberos && \
 docker-php-ext-install imap

## Install Zip extension and it's dependencies
## RUN apt-get install -y zlib1g zlib1g-dev

RUN docker-php-ext-install zip

RUN adduser sugar --disabled-password --disabled-login --gecos ""
RUN sed -i "s#APACHE_RUN_USER=.*#APACHE_RUN_USER=sugar#" /etc/apache2/envvars \
    && sed -i "s#APACHE_RUN_GROUP=.*#APACHE_RUN_GROUP=sugar#" /etc/apache2/envvars

## Beef up the php.ini for doing upgrades

COPY ./www /var/www/html
WORKDIR /var/www/html

