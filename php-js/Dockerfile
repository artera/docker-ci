FROM alpine:latest
RUN apk --no-cache add \
    composer \
    git \
    nodejs \
    nodejs-npm \
    php7 \
    php7-bcmath \
    php7-calendar \
    php7-ctype \
    php7-curl \
    php7-dev \
    php7-dom \
    php7-fileinfo \
    php7-gd \
    php7-gettext \
    php7-gmp \
    php7-iconv \
    php7-intl \
    php7-json \
    php7-mysqli \
    php7-opcache \
    php7-openssl \
    php7-pdo_mysql \
    php7-pear \
    php7-phar \
    php7-posix \
    php7-session \
    php7-simplexml \
    php7-sockets \
    php7-xml \
    php7-xmlreader \
    php7-xmlwriter \
    php7-zip \
    yarn
RUN composer global require --no-plugins --no-scripts "squizlabs/php_codesniffer=*" && \
    rm -rf /root/.composer/cache
ENV PATH="/root/.composer/vendor/bin:${PATH}"
CMD sh
