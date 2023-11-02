# OneSeen

The goal of this repository is to showcase good [Laravel](https://laravel.com) development practices with a simple application.


## Features

- :fire:Burn after reading (the note is destroyed after the first reading)
- :lock: Password protection
- :clipboard: Copy note to clipboard in a click
- :stopwatch: Expiration times, including a "forever" and "burn after reading" option

## How to run OneSeen locally?

I believe you already have Docker installed. If not, just do it on [Mac](https://docs.docker.com/desktop/install/mac-install/), [Windows](https://docs.docker.com/desktop/install/windows-install/) or [Linux](https://docs.docker.com/desktop/install/linux-install/).


Build the `app` image with the following command:

```shell
docker compose build --no-cache
```

>This command might take a few minutes to complete.

When the build is finished, you can run the environment in background mode with:

```shell
docker compose up -d
```

We’ll now run `composer install` to install the application dependencies:

```shell
docker compose exec app composer install
```

Copy the environment settings:

```shell
docker compose exec app cp .env.local .env
```

Migrate DB & seed fake data with the `artisan` Laravel command-line tool:

```shell
docker compose exec app ./artisan migrate:fresh --seed
```

And open http://127.0.0.1:8000 in your favorite browser. Happy using OneSeen! 


## License

This is open-sourced software licensed under the [MIT License](https://github.com/gomzyakov/php-code-style/blob/main/LICENSE).


[![GitHub release](https://img.shields.io/github/release/gomzyakov/oneseen.svg)](https://github.com/gomzyakov/oneseen/releases/latest)
[![license](https://img.shields.io/badge/License-MIT-green.svg)](https://github.com/gomzyakov/oneseen/blob/development/LICENSE)
[![codecov](https://codecov.io/gh/gomzyakov/oneseen/branch/main/graph/badge.svg?token=4CYTVMVUYV)](https://codecov.io/gh/gomzyakov/oneseen)
