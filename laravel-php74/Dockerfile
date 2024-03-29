FROM php:7.4-fpm-alpine

RUN mkdir /var/www/html/public
COPY index.php /var/www/html/public
COPY config/php.ini /usr/local/etc/php
COPY config/php-fpm.conf /usr/local/etc

# Setup GD extension
RUN apk add --no-cache \
  freetype \
  libjpeg-turbo \
  libpng \
  freetype-dev \
  libjpeg-turbo-dev \
  libpng-dev \
  && docker-php-ext-configure gd \
  --with-freetype=/usr/include/ \
  --with-jpeg=/usr/include/ \
  && docker-php-ext-install -j$(nproc) gd \
  && docker-php-ext-enable gd \
  && apk del --no-cache \
  freetype-dev \
  libjpeg-turbo-dev \
  libpng-dev \
  && rm -rf /tmp/*

RUN apk add libzip-dev
RUN docker-php-ext-install pdo pdo_mysql zip bcmath

# Install PHP Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/html