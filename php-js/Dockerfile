FROM php:alpine
RUN apk --no-cache add \
    composer \
    git \
    jq \
    nodejs \
    nodejs-npm \
    yarn \
    bzip2-dev \
    enchant-dev \
    libpng-dev \
    gmp-dev \
    imap-dev \
    icu-dev \
    aspell-dev \
    libzip-dev
RUN docker-php-ext-install -j$(nproc) bcmath bz2 calendar \
    enchant exif gd gettext gmp imap intl opcache pcntl \
    pdo_mysql pspell sockets zip
RUN composer global require --no-plugins --no-scripts "squizlabs/php_codesniffer=*" && \
    rm -rf /root/.composer/cache
ENV PATH="/root/.composer/vendor/bin:${PATH}"
CMD sh
