# Docker LEMP

This is my Docker LEMP setup. My goal was having it run on a Raspberry Pi 4, so I needed multiarch images. It's thought with Laravel in mind (especially this readme), but it's definitely usable with any PHP project.

This is rocking:

- PHP 7.4
- Maria DB
- Nginx

## Usage

What I want is something I can add as a submodule to existing project. So you probably saftely do it on your end too.

Once it's done, make sure you have your `.env` file, run `docker-compose up -d` then, if applicable to your usage: `docker-compose --project-directory=./docker-lemp exec app php artisan storage:link && docker-compose --project-directory=./docker-lemp exec app php artisan key:generate`.

Database user and password is set in `docker-compose.yml`, and your database host is `db`.

## Running commands

Otherwise, you can run commands from your root directory of your project:

- Composer: `docker-compose --project-directory=./docker-lemp exec app composer <COMMAND>`
- Artisan: `docker-compose --project-directory=./docker-lemp exec app php artisan <COMMAND>`

If you run the commands from within `docker-lemp`'s folder, you can drop `--project-directory=./docker-lemp`.

## Thanks

This setup was shamefully stolen, and built upon, [Crater](https://github.com/bytefury/crater)'s own file. Thank you for having the simplest, yet working, LEMP setup I could find!
