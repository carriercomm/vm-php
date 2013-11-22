# Development Server

## Overview

The purpose of these [Puppet][puppet] scripts is to create a development environment for a single website or application.
In the future, I hope to abstract these Puppet scripts into a more modular form. For now, they suit
my own immediate needs.

## Software

* nginx
* php 5.5.6
* mysql
* memcached

## Notable PHP Extensions

This VM configuration provides out-of-the-box support for xdebug and xhprof. Remote
profiling with xdebug is possible on host port 9000 (mapped to guest port 9000 by
VirtualBox). Profiling with the xhprof UI is available on guest port 8081.

* curl
* gd
* intl
* json
* mbstring
* mcrypt
* memcache
* openssl
* pdo
* pdo_mysql
* pdo_sqlite
* mysqlnd
* xdebug
* xhprof

## Getting Started

1. Clone this repository to your computer
2. Specify your MySQL database settings in `provision/modules/mysql/manifests/params.pp`
3. Specify your nginx website domain in `provision/modules/nginx/manifests/params.pp`
4. Run `vagrant up`

After the virtual machine is running, update `/etc/hosts` to point your website's
domain name to `192.168.33.10`. You can access the development website on port `8080` and
the xhprof UI on port `8081`.

## How to Contribute

1. Fork this repository
2. Create a new branch for each feature or improvement
3. Send a pull request from your feature branch

It is very important to separate new features or improvements into separate feature branches, and to send a
pull request for each branch. This allows us to review and pull in new features or improvements individually.

## Requirements

You'll need the following software installed on your local machine:

* VirtualBox
* Vagrant
* Terminal/Console

## Copyright

Copyright 2013, [Josh Lockhart][josh]

## License

MIT Public License

[puppet]: http://puppetlabs.com/
[josh]: http://www.joshlockhart.com/
