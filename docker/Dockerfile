FROM sylius/nginx-php-fpm:latest

WORKDIR /var/www/html

RUN curl -sL https://deb.nodesource.com/setup_9.x | bash -
RUN apt-get update && apt-get install -y \
        nodejs \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev

RUN npm install -g yarn

RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd

USER root
# entrypoint.d scripts
COPY entrypoint.d/* /entrypoint.d/

# nginx configuration
COPY nginx/nginx.conf /etc/nginx/nginx.conf
COPY nginx/sylius_params /etc/nginx/sylius_params

RUN chown www-data.www-data /etc/nginx/sylius_params
RUN chown www-data -R /var/www/html