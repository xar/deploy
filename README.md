# Deploy

<p align="center">
  <a href="https://travis-ci.org/itsjeffro/deploy"><img src="https://travis-ci.org/itsjeffro/deploy.svg?branch=master" alt="Build Status"></a>
</p>

## Introduction
Deploy provides zero-downtime deployment for existing Laravel applications.

## Installation
Include the repository link within your composer.json and run composer to install the package:
```
composer install
```

Next, you will need to register the package's service provider class under the providers array 
in the config/app.php configuration file.

```
Deploy\DeployServiceProvider::class
```

Publish the package's config and assets:
```
php artisan vendor:publish --tag=deploy-config
php artisan vendor:publish --tag=deploy-assets
```

Run the package's migrations:
```
php artisan migrate
```

### Configuration
After publishing the assets, the primary config file will be located in config/deploy.php. This configuration file allows
you to setup the providers (Github and/or Bitbucket) and SSH settings.

The following providers are available:

- Bitbucket
- Github