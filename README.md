# Laravel Countries

[![Total Downloads](https://poser.pugx.org/admsys/laravel-countries/downloads.svg)](https://packagist.org/packages/admsys/laravel-countries)
[![Latest Stable Version](https://poser.pugx.org/admsys/laravel-countries/v/stable.svg)](https://packagist.org/packages/admsys/laravel-countries)
[![Latest Unstable Version](https://poser.pugx.org/admsys/laravel-countries/v/unstable.svg)](https://packagist.org/packages/admsys/laravel-countries)

Laravel Countries is a bundle for Laravel, providing Almost ISO 3166_2, 3166_3, currency, Capital and more for all countries.


## Installation

    composer require admsys/laravel-countries

Edit `app/config/app.php` and add the `provider` and `filter`

    'providers' => [
        'Admsys\Countries\CountriesServiceProvider',
    ]

Now add the alias.

    'aliases' => [
        'Countries' => 'Admsys\Countries\CountriesFacade',
    ]


## Model

You can start by publishing the configuration. This is an optional step, it contains the table name and does not need to be altered. If the default name `countries` suits you, leave it. Otherwise run the following command

    $ php artisan vendor:publish

Next generate the migration file:

    $ php artisan countries:migration

It will generate the `<timestamp>_setup_countries_table.php` migration and the `CountriesSeeder.php` seeder. To make sure the data is seeded insert the following code in the `seeds/DatabaseSeeder.php`

    //Seed the countries
    $this->call('CountriesSeeder');
    $this->command->info('Seeded the countries!');

You may now run it with the artisan migrate command:

    $ php artisan migrate --seed

After running this command the filled countries table will be available
