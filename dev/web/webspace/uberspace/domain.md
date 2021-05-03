# Domain

## Einrichten

```
ssh serien
cd html
git clone https://github.com/serienguide/serienguide.git
uberspace web domain add sandbox.serienguide.tv
ln -s /var/www/virtual/$USER/html/serienguide/public /var/www/virtual/$USER/sandbox.serienguide.tv
```

### Cronjob

```
crontab -e
```

```bash
* * * * * cd ~/html/hof-sundermeier && php artisan schedule:run >> /dev/null 2>&1
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
php artisan migrate --force
php artisan storage:link
```