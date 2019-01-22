FROM php:7-cli
RUN apt-get update -qq \
    && apt-get install -qq -y apt-transport-https lsb-release git libzip-dev gnupg2 \
    && curl -sL https://deb.nodesource.com/setup_10.x | bash - \
    && curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
    && echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list \
    && apt-get install -qq -y nodejs yarn \
    && rm -rf /var/lib/apt/lists/*
RUN docker-php-ext-install -j$(nproc) zip \
    && php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php -r "if (hash_file('sha384', 'composer-setup.php') === '93b54496392c062774670ac18b134c3b3a95e5a5e5c8f1a9f115f203b75bf9a129d5daa8ba6a13e2cc8a1da0806388a8') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" \
    && php composer-setup.php --install-dir=/usr/bin --filename=composer \
    && php -r "unlink('composer-setup.php');"
RUN composer global require --no-plugins --no-scripts "squizlabs/php_codesniffer=*" && \
    rm -rf /root/.composer/cache
ENV PATH="/root/.composer/vendor/bin:${PATH}"
CMD sh
