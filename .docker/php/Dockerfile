FROM php:7.4.1-apache
WORKDIR /var/www/html
RUN apt update -y && apt install -y zlib1g-dev libpng-dev libjpeg-dev
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install calendar
RUN docker-php-ext-configure gd --with-jpeg && docker-php-ext-install gd
RUN a2enmod rewrite headers