# Laravel

## New

- [Quick setup Laravel (with Tailwind scaffold)](https://martinbetz.eu/article/quick-setup-laravel-extended)
- [Laravel Boilerplate](https://github.com/rappasoft/laravel-boilerplate)

Ich habe mir ein [CLI Tool](https://github.com/danielsundermeier/butler) programmiert, das ein neues Laravel Projekt einrichtet, damit ich direkt starten kann.

```
butler laravel:new name
```

## Artikel

- [Laravel beyond CRUD](https://stitcher.io/blog/laravel-beyond-crud)
- [Building and Deploying Laravel with Github Actions](https://driesvints.com/blog/building-and-deploying-laravel-with-github-actions/)
- [Laravel Playground](https://laravelplayground.com/#/)
- [laravel-best-practices](https://github.com/alexeymezenin/laravel-best-practices#follow-laravel-naming-conventions)
- [How to use GitHub Actions build matrix to deploy artifacts to multiple servers](https://philo.dev/how-to-use-github-actions-build-matrix-to-deploy-artifacts-to-multiple-servers/)
- [Larastreamers](https://larastreamers.com/)
- [Laravel Examples](https://laravelexamples.com/)
- [Outputting Eloquent query unparameterized in Laravel](https://www.amitmerchant.com/outputting-eloquent-query-unparameterized-in-laravel/)
- [ArchTech Forum](https://forum.archte.ch/) - a community specifically for advanced discussions
- [Larger Laravel Projects: 12 Things to Take Care Of](https://laraveldaily.com/larger-laravel-projects-12-things-to-take-care-of/)

## Blogs

- [Tighten](https://tighten.co/blog/)
- [Mastering Laravel](https://masteringlaravel.io/)

## Packages

- [A clean and beautiful API to read Excel/CSV sheet](https://github.com/mahmudkuet11/sheet)
- [Feedback Component](https://github.com/mydnic/laravel-feedback-component)
- [Easily tail your logs](https://github.com/spatie/laravel-tail)
- [Laravel Passwordless Login](https://github.com/grosv/laravel-passwordless-login)
- [Laravel Schematics](https://github.com/mtolhuys/laravel-schematics)
- [Laravel Package Development](https://laravelpackage.com/)

## Livewire

- [Livewire](https://laravel-livewire.com)

## Valet

- Wenn es nicht geht: 
```
brew upgrade
```

```
valet install
```

## Traits

public function initializeTRAITNAME

```
namespace App\Traits;

trait Unguarded
{
    public static function bootUnguarded()
    {
        static::creating(function ($model) {
            // 
        });
    }

    public function initializeUnguarded()
    {
        self::$unguarded = true;
        $this->guarded = [];
    }
}
```

## Attributes

- [Tracking model attribute changes in Laravel](https://www.amitmerchant.com/tracking-model-attribute-laravel/)

## Routes

- [Handy RegEx Constraints in Laravel Routes](https://pineco.de/handy-regex-constraints-in-laravel-routes/)

### Batch

- BatchController
    + POST: index_route/batch
    + PUT: index_route/batch
    + DELTE: index_route/batch

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