CeleryBundle
=============

This bundle provides an interface to submit Celery jobs

[![Build Status](https://travis-ci.org/hautelook/Celery.png?branch=master)](https://travis-ci.org/hautelook/Celery)

## Introduction

This bundle provides a service to submit Celery jobs. The jobs are objects that need to implement the `CeleryJobInterface`.

## Installation

Simply run `composer install` assuming you have installed composer.phar or composer binary (or add to your `composer.json` and run composer install:

```bash
$ composer require hautelook/celery-bundle
```

You can follow `dev-master`, or use a more stable tag (recommended for various reasons). On the [Github repository](https://github.com/hautelook/CeleryBundle)

Now add the Bundle to your Kernel:

```php
<?php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new Hautelook\CeleryBundle\HautelookCeleryBundle(),
        // ...
    );
}
```

## Configuration

To configure the bundle, edit your `config.yml`, or `config_{environment}.yml`:

## Usage

### Jobs

To start submitting a job, first create a class that represents the job:

#### Accessing the container from the worker

If your worker needs access to the Symfony DI container, you can simply make your worker class implement
`Symfony\Component\DependencyInjection\ContainerAwareInterface`, and the container will be set for you.
