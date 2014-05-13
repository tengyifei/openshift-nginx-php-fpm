# OpenShift Nginx PHP-FPM Cartridge

nginx 1.6.0
php 5.3, 5.4, and 5.5

Forked from getupcloud/openshift-nginx-php-fpm.

## Usage

```bash
$ rhc app create phpfpm https://reflector-getupcloud.getup.io/reflect?github=pinodex/openshift-nginx-php-fpm
$ cd phpfpm
$ echo '<?php phpinfo(); ?>' > php/info.php
$ echo 'Hello World' >> www/static/hello.html
$ git add .
$ git commit -m 'Testing'
$ git push
```

## User-defined configuration

Place your nginx .conf files inside config/nginx.d/. It will be include()ed from "http" scope.
Place your php-fpm .conf files inside config/php-fpm.d/. It will be include()ed from main php-fpm.conf file.

## Notes

A phpinfo.php file is included to test PHP, you should remove that file after testing if you don't want monkeys see your configurations.