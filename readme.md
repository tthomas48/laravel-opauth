# Laravel 4.x [Opauth](http://opauth.org/) Package

### Installation:

Add to your `composer.json` in `require` section following line:

    "socialism/laravel-opauth": "dev-master"

And run `composer update`, after that add the following line at the and of `app/config/app.php` `providers` section:

    'Socialism\LaravelOpauth\LaravelOpauthServiceProvider',


### Usage:

First of all define some route in your `app/routes.php` **it should be a named route**, like this:

```php
Route::any('auth/social/{strategy}/{action?}', ['as' => 'auth.social', function ($strategy, $action = 'request') {
    app('opauth')->run();
}])->where(['strategy' => '.*']);
```

**Note this `'as' => 'auth.social'` section**, again, route should be a named route, just for proper work.

Then you should publish package config:

    php artisan config:publish socialism/laravel-opauth

Now you can configure route to be used and strategies in `app/config/packages/socialism/laravel-opauth/config.php`.
