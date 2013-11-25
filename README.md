# Development Server

## Overview

The purpose of these [Puppet][puppet] scripts is to create a development environment for a single website or application.
In the future, I hope to abstract these Puppet scripts into a more modular form. For now, they suit
my own immediate needs.

## Getting Started

1. Clone this repository to your computer
2. Specify your MySQL database settings in `provision/modules/mysql/manifests/params.pp`
3. Specify your nginx website domain in `provision/modules/nginx/manifests/params.pp`
4. Run `vagrant up`

When your virtual machine is ready:

* Point your website domain to `192.168.33.10` in `/etc/hosts`
* Access your website on guest port `8080`
* Access the xhprof UI on guest port `8081`
* Access MySQL on host port `8306`
* Listen for remote xdebug communication on host port `9000`

Your website's public document root is the `public/` directory.

## System Requirements

* UNIX or Linux OS
* VirtualBox
* Vagrant
* Terminal/Console

## Included Software

### Ubuntu Precise 12.04 LTS

I use the default `precise64` base Vagrant box.

### nginx 1.1.19

I use the defualt Ubuntu 12.04 LTS `nginx` package.

### php 5.5.6

I use the Ondřej Surý custom PPA to install PHP and related extensions. This allows me to use the latest PHP version while avoiding compiling PHP from source. This includes the following PHP extensions:

#### xhprof

I include the xhprof extension and xhprof GUI. The GUI is available on guest port `8081`.

#### xdebug

I include the xdebug extension. This extension will send remote debugging information to host port `9000` for integration with IDEs like PHPStorm.

#### All Extensions

* bcmath
* bz2
* calendar
* cgi-fcgi
* Core
* ctype
* curl
* date
* dba
* dom
* ereg
* exif
* fileinfo
* filter
* ftp
* gd
* gettext
* hash
* iconv
* intl
* json
* libxml
* mbstring
* mcrypt
* memcached
* mhash
* mysql
* mysqli
* mysqlnd
* openssl
* pcre
* PDO
* pdo_mysql
* pdo_sqlite
* Phar
* posix
* readline
* Reflection
* session
* shmop
* SimpleXML
* soap
* sockets
* SPL
* sqlite3
* standard
* sysvmsg
* sysvsem
* sysvshm
* tidy
* tokenizer
* wddx
* xdebug
* xhprof
* xml
* xmlreader
* xmlwriter
* Zend OPcache
* zip
* zlib
* Xdebug
* Zend OPcache

### mysql 5.5.34

I use the defualt Ubuntu 12.04 LTS `mysql-server` package. However, I also use a custom-tuned `my.cnf` file generated by the [Percona Configuration Wizard](http://tools.percona.com/).

### memcached 1.4.13

I use the defualt Ubuntu 12.04 LTS `memcached` package.

## How to Contribute

1. Fork this repository
2. Create a new branch for each feature or improvement
3. Send a pull request from your feature branch

It is very important to separate new features or improvements into separate feature branches, and to send a
pull request for each branch. This allows us to review and pull in new features or improvements individually.

## Copyright

Copyright 2013, [Josh Lockhart][josh]

## License

MIT Public License

[puppet]: http://puppetlabs.com/
[josh]: http://www.joshlockhart.com/
