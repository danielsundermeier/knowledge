# Deployment Skript

Ich habe ein [Package](https://github.com/danielsundermeier/laravel-deploy) programmiert, damit ich es nicht immer neu einrichten muss.

## Controller

DeploymentController

```
<?php

namespace App\Http\Controllers;

use Illuminate\Http\Request;
use Symfony\Component\Process\Exception\ProcessFailedException;
use Symfony\Component\Process\Process;

class DeploymentController extends Controller
{
    public function store(Request $request)
    {
        $githubPayload = $request->getContent();
        $githubHash = $request->header('X-Hub-Signature');

        $localToken = config('app.deploy_secret');
        $localHash = 'sha1=' . hash_hmac('sha1', $githubPayload, $localToken, false);

        // if (! hash_equals($githubHash, $localHash))
        // {
        //     return abort(404);
        // }

        if (! $githubHash)
        {
            return abort(404);
        }

        $root_path = base_path();
        $process = new Process('cd ' . $root_path . '; sh ./deploy.sh');
        $process->run();

        // executes after the command finishes
        if (!$process->isSuccessful())
        {
            throw new ProcessFailedException($process);
        }

        echo $process->getOutput();
    }
}
```

## Skript

deploy.sh

```
#!/bin/sh

echo "Deploying..."

git stash
git pull
mv .env.production .env
php artisan migrate --force
php artisan queue:restart
composer install  > /dev/null 2>&1 & echo $! #--no-interaction --no-dev --prefer-dist
npm install > /dev/null 2>&1 & echo $!
npm run production > /dev/null 2>&1 & echo $!

echo "Deployed"
```

## CSRF Token

[Disabling CSRF for Specific Routes - Laravel 5](https://www.camroncade.com/disable-csrf-for-specific-routes-laravel-5/)

VerifyCsrfToken.php

```
<?php

namespace App\Http\Middleware;

use Illuminate\Foundation\Http\Middleware\VerifyCsrfToken as Middleware;

class VerifyCsrfToken extends Middleware
{
    /**
     * Indicates whether the XSRF-TOKEN cookie should be set on the response.
     *
     * @var bool
     */
    protected $addHttpCookie = true;

    /**
     * The URIs that should be excluded from CSRF verification.
     *
     * @var array
     */
    protected $except = [
        'deploy',
    ];
}
```