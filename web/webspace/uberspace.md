# Uberspace

## Dateisystem

### Sym Link

#### Uberspace

[Dokumnetation](https://wiki.uberspace.de/domain:subdomain)

```
ln -s /var/www/virtual/$USER/html/cardmonitor/public /var/www/virtual/$USER/www.cardmonitor.de
```

#### Agrarmonitor

```
ln -s /var/www/share/Agrarmonitor-API-DEV/public /var/www/share/sandbox.agrarmonitor.de/htdocs
```

## Supervisor

### Installieren

```
cd ~/etc/services.d
nano cardmonitor.ini
```

```
[program:cardmonitor]
command=php /home/serien/html/cardmonitor/app/artisan queue:work --tries=3
autostart=yes
autorestart=yes
```

```
supervisorctl reread
supervisorctl update
```

### Weitere Befehle

List Services

```
supervisorctl status
```

Logs

```
supervisorctl tail -f cardmonitor
```

## Domains

### Hinzufügen

```
uberspace web domain add lifeos.serienguide.tv
```

- DNS umstellen
- Ordner mit Projket erstellen
- .htaccess bearbeiten

```
...
    RewriteEngine On
    RewriteBase /
...
```

Symlink erstellen
```
ln -s /var/www/virtual/$USER/html/lifeos/public /var/www/virtual/$USER/lifeos.serienguide.tv
```



## Mails

### Domain anlegen

[Anleitung](https://manual.uberspace.de/mail-domains.html)

```
uberspace mail domain add cardmonitor.de
```

```
The mailserver's configuration has been adapted.
Now you can use the following record for your dns:
  MX  -> tempel.uberspace.de
  TXT -> v=spf1 mx ~all
```

DNS Einträge ändern
MX: tempel.uberspace.de
TXT: v=spf1 mx ~all

### Mailkonto anlegen

[Anleitung](https://manual.uberspace.de/mail-access.html)

```
uberspace mail user add info
```

### Zugangsdaten

Server: tempel.uberspace.de
Username: E-Mail Adresse (info@cardmonitor.de)
Passwort: Wie vergeben beim Account erstellen

### Weiterleitung

.qmail-NAME Datei im Home verzeichnis erstellen und die E-Mail Adresse, zu der Weitergeleitet werden soll eintragen.

```
touch .qmail-daniel
nano .qmail-daniel
```

.qmail-daniel
```
info@cardmonitor.de
```