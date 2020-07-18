# Laravel

## New

- [Quick setup Laravel (with Tailwind scaffold)](https://martinbetz.eu/article/quick-setup-laravel-extended)

## Artikel

- [Laravel beyond CRUD](https://stitcher.io/blog/laravel-beyond-crud)
- [Building and Deploying Laravel with Github Actions](https://driesvints.com/blog/building-and-deploying-laravel-with-github-actions/)
- [Laravel Playground](https://laravelplayground.com/#/)

## Blogs

[Tighten](https://tighten.co/blog/)

## Packages

- [A clean and beautiful API to read Excel/CSV sheet](https://github.com/mahmudkuet11/sheet)
- [Feedback Component](https://github.com/mydnic/laravel-feedback-component)
- [Easily tail your logs](https://github.com/spatie/laravel-tail)
- [Laravel Passwordless Login](https://github.com/grosv/laravel-passwordless-login)
- [Laravel Schematics](https://github.com/mtolhuys/laravel-schematics)

## Valet

- Wenn es nicht geht: 
```
brew upgrade
```

## Traits

public function initializeTRAITNAME

```
namespace App\Traits;

trait Unguarded
{
    public function initializeUnguarded()
    {
        self::$unguarded = true;
        $this->guarded = [];
    }
}
```

## Attributes

- [Tracking model attribute changes in Laravel](https://www.amitmerchant.com/tracking-model-attribute-laravel/)

## NULL Object Pattern

### Relationships

```
    public function relationship() : HasOne
    {
        return $this->hasOne(Relationship::class)->withDefault([
            'foo' => 'bar',
        ]); 
    }
```