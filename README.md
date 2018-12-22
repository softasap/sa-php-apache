sa-php-apache
=============
[![Build Status](https://travis-ci.org/softasap/sa-php-apache.svg?branch=master)](https://travis-ci.org/softasap/sa-php-apache)


Basic role for php-apache install, optional pre-configured xdebug support, optional global composer installation as composer{{php_version}}


Example of usage:

Simple

```YAML

     - {
         role: "sa-apache"
       }


     - {
         role: "sa-php-apache"
       }


```

Advanced

see box-example for full featured lamp install.

```YAML

     - {
         role: "sa-php-apache",
         option_install_xdebug: true,
         php_xdebug_version: 2.5.5,
         xdebug_remote_enable: 1
         # IMPORTANT - SETTING BELOW TO 1 ON PROD SERVERS RESULTS TO EXPLOIT
         # AS  xdebug_remote_host is ignored
         xdebug_remote_connect_back: 0
         xdebug_remote_host: "127.0.0.1"


         option_install_composer: true,         

         php_family: default, #  5.6 | 7.0 | hhvm | default

         pkg_dependencies:
           - git
           - curl
           - python-dev
           - libmysqlclient-dev
           - unzip

         php_extensions:
           - "{{php_module_prefix}}-mysql"
           - "{{php_module_prefix}}-intl"
           - "{{php_module_prefix}}-xmlrpc"
           - "{{php_module_prefix}}-curl"
           - "{{php_module_prefix}}-gd"

         timezone: "Europe/London",


       }


```


Usage with ansible galaxy workflow
----------------------------------

If you installed the `sa-php-apache` role using the command


`
   ansible-galaxy install softasap.sa-php-apache
`

the role will be available in the folder `library/softasap.sa-php-apache`
Please adjust the path accordingly.

```YAML

     - {
         role: "softasap.sa-php-apache"
       }

```




Copyright and license
---------------------

Code is dual licensed under the [BSD 3 clause] (https://opensource.org/licenses/BSD-3-Clause) and the [MIT License] (http://opensource.org/licenses/MIT). Choose the one that suits you best.

Reach us:

Subscribe for roles updates at [FB] (https://www.facebook.com/SoftAsap/)

Join gitter discussion channel at [Gitter](https://gitter.im/softasap)

Discover other roles at  http://www.softasap.com/roles/registry_generated.html

visit our blog at http://www.softasap.com/blog/archive.html
