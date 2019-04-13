##
# This is Dockerfile for build php container with dependencies
# run docker build --file DockerfilePHP -t php7.2:latest
##
FROM php:7.2-fpm

RUN apt-get update && apt-get install -y zlib1g-dev libicu-dev g++ libpng-dev
RUN docker-php-ext-install pdo pdo_mysql
RUN docker-php-ext-configure intl
RUN docker-php-ext-install intl
RUN docker-php-ext-install mbstring
RUN docker-php-ext-install zip
RUN docker-php-ext-install gd
RUN docker-php-ext-enable gd
RUN docker-php-ext-enable intl

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /usr/share/nginx/html

#EXPOSE 9000
#CMD ["php", "artisan key:generate"]
