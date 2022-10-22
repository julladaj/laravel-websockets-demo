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

## Credits

- [Marcel Pociot](https://github.com/mpociot)
- [Freek Van der Herten](https://github.com/freekmurze)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.