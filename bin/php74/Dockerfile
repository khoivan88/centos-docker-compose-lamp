FROM php:7.4-fpm-alpine

# Surpresses debconf complaints of trying to install apt packages interactively
# https://github.com/moby/moby/issues/4032#issuecomment-192327844
 
# ARG DEBIAN_FRONTEND=noninteractive

# Update
RUN yum -y update --fix-missing && \
    yum upgrade -y && \
    yum --no-install-recommends install -y apt-utils && \
    rm -rf /var/lib/apt/lists/*


# # Install useful tools and install important libaries
# RUN yum -y update && \
#     yum -y --no-install-recommends install curl wget unzip git vim \
# openssl && \
#     rm -rf /var/lib/apt/lists/* && \

# Install composer for PHP
# RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# # Install xdebug
# RUN pecl install xdebug-2.8.0 && \
#     docker-php-ext-enable xdebug

# # Install redis
# RUN pecl install redis-5.1.1 && \
#     docker-php-ext-enable redis

# Other PHP7 Extensions
RUN docker-php-ext-install mysql && \
    docker-php-ext-install gd && \
    docker-php-ext-install mysqli && \
    docker-php-ext-install curl && \
    docker-php-ext-install tokenizer && \
    docker-php-ext-install json && \
    docker-php-ext-install zip && \
    docker-php-ext-install -j$(nproc) intl && \
    docker-php-ext-install mbstring && \
    docker-php-ext-install pear && \
    docker-php-ext-install zlib-devel && \
    docker-php-ext-install ghostscript && \
    docker-php-ext-install ImageMagick && \
    docker-php-ext-install libreoffice

# # Install Freetype 
# RUN yum -y update && \
#     yum --no-install-recommends install -y libfreetype6-dev \
# libjpeg62-turbo-dev \
# libpng-dev && \
#     rm -rf /var/lib/apt/lists/* && \
#     docker-php-ext-configure gd

# Enable apache modules
RUN a2enmod rewrite headers

# Cleanup
RUN rm -rf /usr/src/*
