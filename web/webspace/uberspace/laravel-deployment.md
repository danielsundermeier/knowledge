# Laravel Deployment

## .htaccess

RewriteBase in .htaccess im Projket setzen.
Wenn es fehlt kommt es zu einem Weiterleitungsfehler.

.htaccess 
```
...
    RewriteEngine On
    RewriteBase /
...
```

## Domain erstellen

```
uberspace web domain add lifeos.serienguide.tv
```

Antwort:
```
The webserver's configuration has been adpated.
Now you can use the following records for your dns:
    A -> 185.26.156.55
    AAAA -> 2a00:d0c0:200:0:b9:1a:9c:37
```

<!-- TODO: Rückgabe -->

## DNS

www.namecheap.com -> DNS Einträge erstellen

- A
- AAA

## git clone

```
ssh serien
cd html
git clone https://github.com/danielsundermeier/lifeos.git
```

## Symlink

```
ln -s /var/www/virtual/$USER/html/lifeos/public /var/www/virtual/$USER/lifeos.serienguide.tv
```

## Deploy

deploy.sh Skript muss ausgeführt werden.

Jetzt ist die Webseite unter lifeos.serienguide.tv zu erreichen

## Skript

Skript zur Automatisierung schreiben