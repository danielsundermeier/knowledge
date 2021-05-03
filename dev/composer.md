# Composer

You will need to perform a composer update in your Laravel application whenever you make changes to the composer.json file of your package or any providers it registers.

## Self Update

```
composer self-update
```

## Memory

Bei v2 nicht mehr benötigt

```
COMPOSER_MEMORY_LIMIT=2G composer require jeroen-g/laravel-packager --dev
```

## Dependency

```
composer show --tree
```

## Link

- [How to pull GitHub repositories](https://www.amitmerchant.com/how-to-pull-github-repositories-as-composer-packages-in-php/)

