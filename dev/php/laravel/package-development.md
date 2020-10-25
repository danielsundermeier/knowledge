# Package Development

## Ablauf

Ich habe mir ein [CLI Tool](https://github.com/danielsundermeier/butler) programmiert, das mir viel Arbeit abnimmt.  

### New

im Root Ordner des Projekts, in dem ich das Package entwickeln möchte.
im Ordner /packages/danielsundermeier/package-name wird eine Vorlage erstellt und im Projekt lokal per Composer eingebunden.

```
butler package:new danielsundermeier/package-name D15r\\PackageNamespace --laravel
```

### Publish

- Git Repository wird erstellt, alles commited und veröffentlicht
- --release=0.1.0 erstellt einen neuen Release
- Package bei Packagist.org registrieren?

```
butler package:publish danielsundermeier/package-name --release="0.1.0"
```

### Remove

```
butler package:remove danielsundermeier/package-name --require
```

### Clone

```
butler package:clone danielsundermeier/package-name https://github.com/danielsundermeier/package-name
```

### Push

```
butler package:push danielsundermeier/package-name "Commit message (optional)" --release="0.2.0"
```

## Links

### Artikel

- [Package Development](https://laravel.com/docs/packages)
- [Creating a Laravel specific package](https://johnbraun.blog/posts/creating-a-laravel-package-1)
- [Laravel Package Boilerplate](https://laravelpackageboilerplate.com/)