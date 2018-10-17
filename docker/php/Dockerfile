FROM php:7.2.10-apache-stretch

RUN a2enmod rewrite

RUN apt-get update \
    && apt-get install -y git unzip vim libicu-dev zlib1g-dev mysql-client libpng-dev libjpeg-dev libpq-dev \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/* \
 	&& docker-php-ext-configure gd --with-png-dir=/usr --with-jpeg-dir=/usr \
    && docker-php-ext-install intl zip mysqli gd mbstring pdo pdo_mysql pdo_pgsql

RUN usermod -u 1000 www-data && groupmod -g 1000 www-data