```bash
FROM php:7.2.10

RUN apt-get update -y && apt-get install -y openssl zip unzip git

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN docker-php-ext-install pdo mbstring

RUN apt-get update && apt-get install -y libpq-dev && docker-php-ext-install pdo pdo_pgsql

WORKDIR /app
COPY . /app
# RUN composer install

CMD php artisan serve --host=127.0.0.1 --port=3001
EXPOSE 3001
```