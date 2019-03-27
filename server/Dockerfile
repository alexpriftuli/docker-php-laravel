FROM alpine:3.8
LABEL MAINTAINER "alexandro.priftuli@gmail.com"

# Install php7, nginx, nodeJs, openrc ...
RUN apk add --update curl bash openrc libpng-dev mysql-client nginx nodejs nodejs-npm php7 php7-ctype php7-curl php7-dom php7-fpm php7-gd php7-json php7-mbstring php7-phar php7-session php7-xml php7-xmlwriter php7-zip php7-dev gcc musl-dev make
ADD root/.bashrc /root/

# Install Composer
RUN curl -O https://getcomposer.org/composer.phar && mv composer.phar /usr/local/bin/composer && chmod 755 /usr/local/bin/composer

# Install gulp
RUN npm install -g gulp-cli

# Install xdebug
ENV XDEBUG_VERSION 2.7.0
RUN curl -sSL -o /tmp/xdebug-${XDEBUG_VERSION}.tgz http://xdebug.org/files/xdebug-${XDEBUG_VERSION}.tgz && \
    cd /tmp && tar -xzf xdebug-${XDEBUG_VERSION}.tgz && cd xdebug-${XDEBUG_VERSION} && phpize && ./configure --enable-xdebug && make && make install && \
    rm -rf /tmp/xdebug*
RUN echo "zend_extension=/usr/lib/php7/modules/xdebug.so" >> /etc/php7/php.ini
ADD php/conf.d/xdebug.ini /etc/php7/conf.d/

# Install phpunit
RUN curl -sSL -o /usr/bin/phpunit https://phar.phpunit.de/phpunit.phar && chmod +x /usr/bin/phpunit

EXPOSE 80