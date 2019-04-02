Docker image for PHP applications
========================================

Base image from [phusion/baseimage:0.11](https://github.com/phusion/baseimage-docker)

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
* xml
* zip
* dev
* xdebug

Additional tool list:
* composer
* nginx

Additional startup bash script list:
* ```alias ll='ls -la';```

Default ports:
nginx: `81`
mysql: `3307`
