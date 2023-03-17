FROM php:7.3-fpm-alpine

RUN mkdir /var/www/html/public
COPY index.php /var/www/html/public
COPY config/php.ini /usr/local/etc/php
COPY config/php-fpm.conf /usr/local/etc

# Setup GD extension
RUN apk --no-cache add \
  bash \
  freetype \
  freetype-dev \
  libpng \
  libzip-dev \
  libpng-dev \
  libjpeg-turbo-dev

RUN docker-php-ext-install pdo pdo_mysql zip bcmath
RUN docker-php-ext-configure gd --with-jpeg-dir=/usr/include/ && \
  docker-php-ext-install gd

# Install PHP Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/html