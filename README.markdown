Master: [![Build Status](https://api.travis-ci.org/tz-lom/HSPHP.png?branch=master)](http://travis-ci.org/tz-lom/HSPHP)

# HandlerSocker Library for PHP

This library provides an API for communicating with the HandlerSocket plugin for
MySQL compatible databases(MySQL, MariaDB, Percona).

For more information on HandlerSocket, check out the 
[MariaDB Documentation on HandlerSocket here](https://mariadb.com/kb/en/handlersocket/).

## Installation

[Once you have composer installed](https://getcomposer.org/doc/00-intro.md#system-requirements "Getting Started With Composer"),
run the following in your php project directory:

        php composer.phar require tz-lom/hsphp --no-update

# Usage Examples
(removed write operations.)

## Select

```php
$c = new \HSPHP\ReadSocket();
$c->connect();
$id = $c->getIndexId('data_base_name', 'table_name', '', 'id,name,some,thing,more');
$c->select($id, '=', array(42)); // SELECT WITH PRIMARY KEY
$response = $c->readResponse();

//SELECT with IN statement
$c = new \HSPHP\ReadSocket();
$c->connect();
$id = $c->getIndexId('data_base_name', 'table_name', '', 'id,name,some,thing,more');
$c->select($id, '=', array(0), 0, 0, array(1,42,3));
$response = $c->readResponse();
```

