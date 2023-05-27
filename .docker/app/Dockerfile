FROM php:8.2-fpm

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        zip \
        unzip \
        ssh \
        git

COPY --chown=www-data:www-data . /var/www/

RUN composer install \
        --prefer-dist \
        --no-ansi \
        --no-interaction \
        --no-progress \
        --no-scripts \
        --optimize-autoloader

