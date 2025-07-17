FROM php:8.4-fpm

RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip \
    procps \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install \
    pdo_mysql \
    mbstring \
    exif \
    pcntl \
    bcmath \
    gd \
    opcache

COPY --from=composer:2 /usr/bin/composer /usr/bin/composer
RUN composer global require laravel/installer && \
    ln -sf /root/.composer/vendor/bin/laravel /usr/local/bin/ && \
    chmod +x /usr/local/bin/laravel

RUN curl -sL https://deb.nodesource.com/setup_lts.x | bash -
RUN apt-get update && apt-get install -y nodejs
RUN npm install --global yarn
