Docker image with PHP for Laravel
========================================

Base image from [alpine:latest](https://hub.docker.com/_/alpine/)

Additional PHP extension list:
* ctype
* curl
* dom
* fileinfo
* fpm
* gd
* json
* mbstring
* phar
* session
* xml
* xmlwriter
* xdebug

Additional tool list:
* bash
* composer
* gulp-cli
* mysql-client
* nano
* nginx
* node
* npm

Additional startup bash script list:
* ```alias ll='ls -la';```

nginx port set `81`

mysql port `3307`
