FROM php:7.2-apache

RUN apt-get update && apt-get install -y \
        libzip-dev \
        unzip \
        libpq-dev \
        && docker-php-ext-install pdo pdo_pgsql zip

RUN a2enmod rewrite

RUN chmod 777 -R -c /var/www
RUN chmod 777 -R -c /usr/local/etc/php

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Sin npm
# RUN curl -sl https://deb.nodesource.com/setup_8.x | bash -- \
#     && apt-get install -y nodejs \
#     && apt-get autoremove -y

# Instalar Node.js y npm
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash -
RUN apt-get install -y nodejs

RUN apt-get autoremove -y