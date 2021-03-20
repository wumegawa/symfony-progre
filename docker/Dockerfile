FROM php:7.4-fpm

ARG _PROJECT_DIR='/app'

ENV DOCKER_USER='php'
ENV PROJECT_DIR=${_PROJECT_DIR}

WORKDIR /var/www/html${_PROJECT_DIR}

RUN adduser --system --group --disabled-password --shell /bin/bash --home ${_PROJECT_DIR} ${DOCKER_USER}
RUN apt-get update \
    && apt-get install -y zlib1g-dev libzip-dev \
    && docker-php-ext-install pdo pdo_mysql zip

COPY --from=composer /usr/bin/composer /usr/bin/composer
