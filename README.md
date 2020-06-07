# Docker LEMP

This is my Docker LEMP setup. My goal was having it run on a Raspberry Pi 4, so I needed multiarch images. It's thought with Laravel in mind (especially this readme), but it's definitely usable with any PHP project.

This is rocking:

- PHP 7.4
- Maria DB
- Nginx

## Usage

### Running from your project's root

If you are running commands from the `docker-lemp` directory, there's nothing special to do. But most of the time, we do run those from the project's root. If you do so, you should be running them like so:

`docker-compose -f ./docker-lemp/docker-compose.yml <your command>`

This readme takes for granted that your understand this, so it'll not be adding it to all the commands listed.

### Installation

I wanted something that could be added as a submodule to an existing project. It's safe to assume that you could do it yourself too.

Database user and password is set in `docker-compose.yml`, and your database host is `db`.

## Composer and artisan

You can run composer and artisan command using the following:

- Composer: `docker-compose exec app composer <COMMAND>`
- Artisan: `docker-compose exec app php artisan <COMMAND>`

## Thanks

This setup was shamefully stolen, and built upon, [Crater](https://github.com/bytefury/crater)'s own file. Thank you for having the simplest, yet working, LEMP setup I could find!
