FROM php:8.1.2-apache
ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update -y && apt-get install -y sendmail libpng-dev
RUN docker-php-ext-install mysqli pdo pdo_mysql
RUN apt-get update \
    && apt-get install -y libzip-dev \
    && apt-get install -y zlib1g-dev \
    && rm -rf /var/lib/apt/lists/* \
    && docker-php-ext-install zip

RUN docker-php-ext-install mysqli
RUN docker-php-ext-install exif
RUN docker-php-ext-install calendar && docker-php-ext-enable calendar
RUN docker-php-ext-install gd
RUN docker-php-ext-install shmop


RUN a2enmod rewrite