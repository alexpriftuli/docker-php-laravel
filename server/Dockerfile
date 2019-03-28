FROM phusion/baseimage:0.11
MAINTAINER "alexandro.priftuli@gmail.com"

RUN apt-get update
RUN apt-get install -y curl libpng-dev mysql-client unzip
ADD root/.bashrc /root/

# Install php7, nginx, curl ...
RUN apt-get install -y nginx php php-ctype php-curl php-dom php-fpm php-gd php-json php-mbstring php-phar php-xml php-zip php-dev

# Install composer
RUN curl -O https://getcomposer.org/composer.phar && mv composer.phar /usr/local/bin/composer && chmod 755 /usr/local/bin/composer

# Install xdebug
RUN pecl install xdebug
RUN echo "zend_extension=/usr/lib/php/20170718/xdebug.so" >> /etc/php/7.2/fpm/php.ini
ADD php/conf.d/xdebug.ini /etc/php/7.2/mods-available/

# Install phpunit
RUN curl -sSL -o /usr/bin/phpunit https://phar.phpunit.de/phpunit.phar && chmod +x /usr/bin/phpunit

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]