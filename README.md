# Symfony Docker

A [Docker](https://www.docker.com/)-based installer and runtime for the [Symfony](https://symfony.com) web framework, a MySQL database service, full [HTTP/2](https://symfony.com/doc/current/weblink.html) and HTTPS support, an ELK stack for data analytics.

## Getting Started

1. Run `docker-compose up` (the logs will be displayed in the current shell)
2. Open `https://localhost` in your favorite web browser and [accept the auto-generated TLS certificate](https://stackoverflow.com/a/15076602/1352334)
3. **Enjoy!**

## Selecting specific service versions

From the root of the project copy the .env.example Docker Compose environment example file to a .env file.

### Symfony

Use the `SYMFONY_VERSION` environment variable to select a specific Symfony version.

To install a non-stable version of Symfony, use the `STABILITY` environment variable during the build.
The value must be [a valid Composer stability option](https://getcomposer.org/doc/04-schema.md#minimum-stability)) .

Configure them with the related environment variables in the .env file.

### PHP

Use the `PHP_VERSION` environment variable to select a specific PHP version.
Configure them with the related environment variables in the .env file.

### Nginx

Use the `NGINX_VERSION` environment variable to select a specific Nginx version.
Configure them with the related environment variables in the .env file.

### MySQL

Use the `MYSQL_VERSION` environment variable to select a specific MySQL version.
Configure them with the related environment variables in the .env file.

## Debugging

The development stack (defined in the docker-compose.dev.yml file) is shipped with XDdebug configured.
Provision it by setting the COMPOSE_FILE Docker Compose environment variable in the .env file that you can copy from the .env.exmple file.

### Editing Permissions on Linux

If you work on linux and cannot edit some of the project files right after the first installation, you can run `docker-compose run --rm app chown -R $(id -u):$(id -g) .` to set yourself as owner of the project files that were created by the docker container.

## Credits

Created by [Kévin Dunglas](https://dunglas.fr) and sponsored by [Les-Tilleuls.coop](https://les-tilleuls.coop).
