# Use an official PHP 8.0 image with Alpine that includes Composer
FROM php:8.1-fpm-alpine3.18

# Install additional dependencies
RUN apk --no-cache add \
    git \
    libzip-dev

# Install required PHP extensions
RUN docker-php-ext-install zip pdo_mysql

# Install Composer globally
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Set the working directory
WORKDIR /var/www/html

# Expose port 9000 for PHP-FPM
EXPOSE 9000

# Start PHP-FPM in the foreground
CMD ["php-fpm"]
