# Domain

## Einrichten

```
ssh serien
cd html
git clone https://github.com/serienguide/serienguide.git
uberspace web domain add sandbox.serienguide.tv
ln -s /var/www/virtual/$USER/html/serienguide/public /var/www/virtual/$USER/sandbox.serienguide.tv
```

## Projekt installieren

```
cd serienguide
nano .env
sh deploy.sh
```

oder

```
cd serienguide
nano .env
composer install
npm install && npm run production
php aristisan migrate
```