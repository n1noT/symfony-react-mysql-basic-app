# Use the official PHP 8.2 FPM image as the base image
FROM php:8.3-fpm

# Set the working directory to /app
WORKDIR /app/backend

# Install necessary dependencies
RUN apt-get update && \
    apt-get install -y \
    git \
    unzip \
    libzip-dev \
    libpq-dev \
    libonig-dev \
    libicu-dev && \
    docker-php-ext-install pdo_mysql intl && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

RUN echo "extension=intl.so" >> /usr/local/etc/php/conf.d/docker-php-ext-intl.ini

# RUN sudo chmod 777 -R ./public/uploads

# Install Composer globally
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Expose port 9000 for PHP-FPM
EXPOSE 9000