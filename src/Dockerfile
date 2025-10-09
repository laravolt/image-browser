ARG PHP_VERSION='8.4'
ARG BASE_IMAGE="serversideup/php:beta-${PHP_VERSION}-frankenphp"

FROM ${BASE_IMAGE}

# Switch to root so we can do root things
USER root

RUN apt update && \
    apt install -y git zip unzip nodejs npm wget ca-certificates && \
    install-php-extensions bcmath exif gd sockets xdebug intl

RUN npx playwright install-deps

COPY 40-laravolt-link.sh /etc/entrypoint.d/

# Copy shell aliases to both root and www-data user homes
COPY shell/aliases.sh /root/.aliases.sh
COPY shell/bashrc /root/.bashrc

RUN mkdir /var/www/.npm && \
    mkdir /var/www/.cache && \
    chown -R 33:33 "/var/www/.npm" && \
    chown -R 33:33 "/var/www/.cache"

# Clean up
RUN rm -rf /var/lib/apt/lists/* && \
    rm -rf /tmp/* /var/tmp/*

# Drop back to our unprivileged user
USER www-data

COPY package.json /var/www/html/package.json

RUN composer global config allow-plugins.gmta/composer-velocita true && \
    composer global require gmta/composer-velocita && \
    npm install playwright@latest && npx playwright install

# Copy shell configuration
COPY shell/aliases.sh /var/www/.aliases.sh
COPY shell/bashrc /var/www/.bashrc
