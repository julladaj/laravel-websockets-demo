# Laravel WebSockets Demo 🛰

This is a demo application built with the [Laravel WebSockets](https://github.com/beyondcode/laravel-websockets) package.

Be sure to check out the [official documentation](https://docs.beyondco.de/laravel-websockets/).

## Usage

1. Clone this repository
```shell
git clone https://github.com/beyondcode/laravel-websockets-demo.git
```
2. Install composer
```shell
composer install
```
3. Create `.env` file
```shell
cp .env.example .env
```
4. Migrate
```shell
php artisan migrate
```
5. Generate the key
```shell
php artisan key:generate
```
6. Start the server (default is port 6001)
```shell
php artisan websockets:serve
```

## Fix "Laravel PackageManifest.php: Undefined index: name"
Find line 116 and comment it:

```php
$packages = json_decode($this->files->get($path), true);
```
Add two new lines after the above commented line:
```php
$installed = json_decode($this->files->get($path), true);
$packages = $installed['packages'] ?? $installed;
```

## Check for package.json
Make sure it appears as follows:
```json
{
  "private": true,
  "scripts": {
    "dev": "npm run development",
    "development": "cross-env NODE_ENV=development node_modules/webpack/bin/webpack.js --progress --hide-modules --config=node_modules/laravel-mix/setup/webpack.config.js",
    "watch": "npm run development -- --watch",
    "watch-poll": "npm run watch -- --watch-poll",
    "hot": "cross-env NODE_ENV=development node_modules/webpack-dev-server/bin/webpack-dev-server.js --inline --hot --config=node_modules/laravel-mix/setup/webpack.config.js",
    "prod": "npm run production",
    "production": "cross-env NODE_ENV=production node_modules/webpack/bin/webpack.js --no-progress --hide-modules --config=node_modules/laravel-mix/setup/webpack.config.js"
  },
  "devDependencies": {
    "axios": "^0.18",
    "bootstrap": "^4.0.0",
    "cross-env": "^5.1",
    "jquery": "^3.2",
    "laravel-mix": "^2.0",
    "lodash": "^4.17.5",
    "popper.js": "^1.12",
    "vue": "^2.5.17"
  },
  "dependencies": {
    "laravel-echo": "^1.5.0",
    "pusher-js": "^4.3.1"
  }
}
```
## Credits

- [Marcel Pociot](https://github.com/mpociot)
- [Freek Van der Herten](https://github.com/freekmurze)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.