Learning Laravel 5
==================

Notes and processes to remember.

Install via composer
--------------------

    composer global require "laravel/installer=~1.1"

Add global composer to $PATH

    echo 'export PATH=~/.composer/vendor/bin:$PATH' >> /home/vagrant/.bashrc

Create a new project

    laravel new blog

or

    composer create-project laravel/laravel laravel-5-project-name dev-develop --prefer-dist

Update the namespace of the app

    php artisan app:name NamespaceName

Setup the environment

    cp .env.example .env

    APP_ENV=local
    APP_KEY=SomeRandomString
    ...

Routes are now in the controllers
---------------

    # app/Http/Controllers/HomeController.php

    /**
     * @Get("/")
     */
    public function index()
    {
      ...
    }
    
Add any new controllers to the RouteServiceProvider.php

    # app/Providers/RouteServiceProvider.php
    
    protected $scan = [
        ...,
        'app/Http/Controllers/HomeController.php',
    ]
    

