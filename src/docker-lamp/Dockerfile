
# Primero esecificamos que queremos y que version. En este caso, PHP en version 8
FROM php:8.0.0-apache
# Ahora, que version de SO vamos a usar de base. Aqui elegimos debian. Podriamos elegir, por ejemplo
# Debian Buster
ARG DEBIAN_FRONTEND=noninteractive
# RUN es una orden de ejecucion en bash. Esta orden instala php
#Las ordenes subsecuentes son instalaciones de librerías necesarias
RUN docker-php-ext-install mysqli

RUN apt-get update \
    && apt-get install -y sendmail libpng-dev \
    && apt-get install -y libzip-dev \
    && apt-get install -y zlib1g-dev \
    && apt-get install -y libonig-dev \
    && rm -rf /var/lib/apt/lists/* \
    && docker-php-ext-install zip

RUN docker-php-ext-install mbstring
RUN docker-php-ext-install zip
RUN docker-php-ext-install gd
#Este comando es para crear direcciones dinámicas. Cosas de PHP
RUN a2enmod rewrite