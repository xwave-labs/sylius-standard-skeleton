![Sylius](http://demo.sylius.org/assets/shop/img/logo.png)

[![License](https://img.shields.io/packagist/l/Sylius/Sylius.svg)](https://packagist.org/packages/sylius/sylius)
[![Version](https://img.shields.io/packagist/vpre/Sylius/Sylius.svg)](https://packagist.org/packages/sylius/sylius)
[![Build status on Linux](https://img.shields.io/travis/Sylius/Sylius/master.svg)](http://travis-ci.org/Sylius/Sylius)
[![Scrutinizer Quality Score](https://img.shields.io/scrutinizer/g/Sylius/Sylius.svg)](https://scrutinizer-ci.com/g/Sylius/Sylius/)
[![Total Downloads](https://poser.pugx.org/sylius/sylius/downloads)](https://packagist.org/packages/sylius/sylius)

**This is Sylius Standard Edition repository for starting new projects with Docker.**

Sylius is the first decoupled eCommerce framework based on [**Symfony**](http://symfony.com) and [**Doctrine**](http://doctrine-project.org). 
The highest quality of code, strong testing culture, built-in Agile (BDD) workflow and exceptional flexibility make it the best solution for application tailored to your business requirements. 
Enjoy being an eCommerce Developer again!

Powerful REST API allows for easy integrations and creating unique customer experience on any device.

We're using full-stack Behavior-Driven-Development, with [phpspec](http://phpspec.net) and [Behat](http://behat.org)

Documentation
-------------

Documentation is available at [docs.sylius.org](http://docs.sylius.org).

Installation
------------

```bash
$ composer create-project xwave-labs/sylius-docker-skeleton project-name
$ cd project-name
$ docker-compose up -d
$ docker-compose exec app chown www-data -R /var/www/html
$ docker-compose exec --user www-data app php bin/console sylius:install
$ docker-compose exec --user www-data app php bin/console sylius:fixtures:load -n
$ docker-compose exec --user www-data app yarn install
$ docker-compose exec --user www-data app yarn run gulp
```