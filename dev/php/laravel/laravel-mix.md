# laravel mix

## Update auf v6.0

[Upgrade to Mix 6](https://laravel-mix.com/docs/6.0/upgrade)

```bash
npm install laravel-mix@latest
```

package.js
```js
"scripts": {
    "development": "mix",
    "watch": "mix watch",
    "watch-poll": "mix watch -- --watch-options-poll=1000",
    "hot": "mix watch --hot",
    "production": "mix --production"
}

```

webpack.mix.js
```js
mix.js('resources/js/app.js', 'public/js')
    .vue({ version: 2 });
````

app.js
```js
window.Vue = require('vue').default;
```

[[6.0.0-beta.14] [webpack-cli] Invalid configuration object.](https://github.com/laravel-mix/laravel-mix/issues/2633)

```bash
npm uninstall sass
npm uninstall sass-loader
rm -rf node_modules
rm package-lock.json yarn.lock
npm cache clear --force
npm install

npm run development
```
