# Laravel 5 SAML idP

This package allows you to implement your own Identification Provider using the SAML 2.0 standard.

## Installation

Require this package with composer:

```shell
composer require codegreencreative/laravel-samlidp
```

After updating composer, add the ServiceProvider to the providers array in config/app.php

```php
Codegreencreative\Idp\SamlidpServiceProvider::class
```

### Middleware

We will need to update the middleware for guests guard in

## Blade directive

`@samlidpfields` will provide you with the hidden input fields supplied by your Service Provider. Place the directive in your blade file where your login form is located and right after the `<form>` tag.

```blade
<form class="form-horizontal" role="form" method="POST" action="{{ url('/login') }}">
    @samlidpfields
    {{ csrf_field() }}
    ...
</form>
```