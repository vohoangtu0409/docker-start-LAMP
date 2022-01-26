FROM php:7.4.1-apache
WORKDIR /var/www/html
RUN apt update -y && apt install -y zlib1g-dev libpng-dev libjpeg-dev
RUN docker-php-ext-install mysqli bcmath opcache
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install calendar
RUN docker-php-ext-configure gd --with-jpeg && docker-php-ext-install gd
# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

# Use the default development configuration
RUN mv $PHP_INI_DIR/php.ini-development $PHP_INI_DIR/php.ini

RUN a2enmod rewrite headers