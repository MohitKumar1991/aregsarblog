# Installing Laravel using Composer

May 20, 2019 by [Areg Sarkissian](https://aregsar.com/about)

## Introduction

In this post I will detail how we can use the Composer, the PHP package manager, to create a new Laravel project.

I will further show how we can run composer to install the PHP packages for our project and run `Yarn` to install NPM modules for our project.

This post assumes that you have PHP and Composer installed on your local system.

> Note: An alternate Laravel installation CLI tool is available that you can install as a global Composer package. We will avoid using this tool and just use Composer directly to create Laravel projects, using the composer create-project command. This eliminates an additional dependency on the Laravel installer tool that we don't need to install and keep updated.

## Using Composer to create a new Laravel project

We ca run the following composer command to download and create a new Laravel project:

`composer create-project --prefer-dist laravel/laravel:5.8 myapp`

Here we specified `myapp` as the name of our project and `5.8` as the version of Laravel project that we want create.

Since we did not specify a specific version patch such as `5.8.17`, the latest patch will be used.

If we omit the Laravel version, the latest version of the framework will be installed:

`composer create-project --prefer-dist laravel/laravel myapp`

We can run `cd myapp` to see all the project files and directories.

## Installing Composer packages

Since we are using Composer to create the project, Composer will also install the Laravel packages for us which will create the `vendor` directory where the packages are installed.

So running `composer install` from the project directory should indicate that there are no new packages to install.

> Note: If you are using PHP 7.3 and you get an JIT compiler setting error when `composer install` is run, update the JIT compiler setting in your PHP configuration file as detailed in my blog post [Installing Composer PHP Package Manager](https://aregsar.com/blog/2019/installing-composer-php-package-manager).

## Installing NPM modules

If we have NodeJS installed on our system, we can also run `yarn` from the project directory to install NPM modules in our project. If we don't have NodeJS installed, another way to install the NPM packages is to run `yarn` from the project directory using the official Node Docker container:

`docker run --rm -v $(pwd):/app -w /app node yarn`

Either way running the command will create the `node_modules` directory where the NPM modules will be installed.

Running `yarn` will also create the `yarn.lock` dependency file in the project directory.

## Checking the installation using the Artisan CLI

We can running the Laravel `Artisan` CLI command from the project directory to verify our Laravel installation:

`php artisan`

This should list the installed Laravel version and the list of available Artisan commands.

## Running the application

To run our application, we can run a PHP server using the following Artisan command:

`php artisan serve --port=8080`

We should now be able to navigate our web browser to `localhost:8080` to see the Laravel application home page.

In another post I will detail how we can install and configure Laravel `Valet` to serve all our Laravel apps without having to explicitly run a web server.

## Conclusion

In this post I detailed how we can create a new Laravel project with composer, using any version of the Laravel framework.

Thanks for reading.