FROM php:alpine
RUN apk --no-cache add \
    composer \
    git \
    jq \
    nodejs \
    nodejs-npm \
    yarn \
    bzip2 \
    bzip2-dev \
    enchant \
    enchant-dev \
    libpng \
    libpng-dev \
    gmp \
    gmp-dev \
    imap \
    c-client \
    imap-dev \
    icu \
    icu-dev \
    aspell \
    aspell-dev \
    libzip \
    libzip-dev \
    tidyhtml-libs \
    tidyhtml-dev \
    make \
    python3 \
    mariadb-client \
    postgresql-client
RUN docker-php-ext-install -j$(nproc) bcmath bz2 calendar \
    enchant exif gd gettext gmp imap intl opcache pcntl \
    pdo_mysql pspell sockets tidy zip mysqli
RUN apk del \
    bzip2-dev \
    enchant-dev \
    libpng-dev \
    gmp-dev \
    imap-dev \
    icu-dev \
    aspell-dev \
    libzip-dev \
    tidyhtml-dev
RUN composer global require --no-plugins --no-scripts "squizlabs/php_codesniffer=*" && \
    rm -rf /root/.composer/cache
RUN npm install -g pnpm
RUN pip3 --no-cache-dir install jinja2 requests
ENV PATH="/root/.composer/vendor/bin:${PATH}"
CMD sh
