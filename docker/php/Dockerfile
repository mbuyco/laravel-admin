FROM php:7.3-fpm-alpine

# Install packages
RUN apk --no-cache add \
    php7 \
    php7-fpm \
    php7-opcache \
    php7-gd \
    php7-zlib \
    php7-bcmath \
    php7-ctype \
    php7-fileinfo \
    php7-json \
    php7-mbstring \
    php7-openssl \
    php7-pdo \
    php7-tokenizer \
    php7-tokenizer \
    php7-xml \
    composer

# File permissions for laravel
RUN addgroup -g 1000 www
RUN adduser -D -s /bin/sh -G www www

# Copy project files
COPY ./src /app

# Copy directory permissions
COPY --chown=www:www ./src /app

# Set working directory
WORKDIR /app

# Set current user to 'www'
USER www

# Expose port 9000 and start php-fpm server
EXPOSE 9000
CMD ["php-fpm"]