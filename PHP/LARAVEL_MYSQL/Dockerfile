FROM php:7.2-apache

RUN apt-get update && apt-get install -y \
        libzip-dev \
        unzip \
        && docker-php-ext-install mysqli pdo pdo_mysql zip

RUN a2enmod rewrite

RUN chmod 777 -R -c /var/www

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN curl -sl https://deb.nodesource.com/setup_8.x | bash -- \
    && apt-get install -y nodejs \
    && apt-get autoremove -y  