# OpenShift Nginx PHP-FPM Cartridge

Nginx updated to 1.6.0 with PHP 5.3/5.4/5.5.

Forked from [getupcloud/openshift-nginx-php-fpm](https://github.com/getupcloud/openshift-nginx-php-fpm).

## Example Usage

### Command line
Install the [OpenShift RHC Client Tools](https://www.openshift.com/developers/rhc-client-tools-install) first if you haven't installed it yet.
```bash
$ rhc app create myapplicationname https://reflector-getupcloud.getup.io/github/pinodex/openshift-nginx-php-fpm
$ cd myapplicationname
$ echo '<?php phpinfo(); ?>' > www/info.php
$ git add .
$ git commit -m 'Testing'
$ git push
```

### Using OpenShift Console
Use this for your cartridge definition URL [https://reflector-getupcloud.getup.io/github/pinodex/openshift-nginx-php-fpm](https://reflector-getupcloud.getup.io/github/pinodex/openshift-nginx-php-fpm)

## PHP Version

PHP 5.4 will be installed if the "**v**" parameter is not specified. To install other PHP version, just pass the version to the "**v**" parameter.

```bash
$ rhc app create myapplicationname https://reflector-getupcloud.getup.io/github/pinodex/openshift-nginx-php-fpm?v=5.3
```

## User-defined configuration

Place your nginx .conf files inside config/nginx.d/. It will be include()ed from "http" scope.
Place your php-fpm .conf files inside config/php-fpm.d/. It will be include()ed from main php-fpm.conf file.