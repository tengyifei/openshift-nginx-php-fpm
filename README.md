# OpenShift Nginx PHP-FPM Cartridge

nginx 1.6.0
php 5.3, 5.4, and 5.5

Forked from [getupcloud/openshift-nginx-php-fpm](https://github.com/getupcloud/openshift-nginx-php-fpm).

## Example Usage

```bash
$ rhc app create myapplicationname https://reflector-getupcloud.getup.io/reflect?github=pinodex/openshift-nginx-php-fpm
$ cd myapplicationname
$ echo '<?php phpinfo(); ?>' > www/info.php
$ git add .
$ git commit -m 'Testing'
$ git push
```

To select PHP version that will be used in your app, just pass the **v** parameter to the URL. Example:

```bash
$ rhc app create myapplicationname https://reflector-getupcloud.getup.io/reflect?github=pinodex/openshift-nginx-php-fpm\&v=5.4
```

## User-defined configuration

Place your nginx .conf files inside config/nginx.d/. It will be include()ed from "http" scope.
Place your php-fpm .conf files inside config/php-fpm.d/. It will be include()ed from main php-fpm.conf file.