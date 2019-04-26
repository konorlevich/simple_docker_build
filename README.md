My PHPDocker-based docker build
==================================

Development build for my projects

## Getting Started

### Prerequisites

Make sure you have already installed both [docker] and [docker-compose] version  [3 or higher]

### Installing

Clone this repo
```bash
git clone git@github.com:konorlevich/simple_docker_build.git your_directory_name
cd your_directory_name
```
Clone your project to [sources directory](project)
```bash
git clone [your repo name] project
```
Create [phpdocker/.env.local](phpdocker/.env.local)
```bash
cp phpdocker/.env phpdocker/.env.local
```
Put your [CODESTATS_KEY] to [.env.local](phpdocker/.env.local)

And run containers

```bash
docker-compose up -d 
```
This command will automatically:
- build images
- run containers
- run `composer install` in the [root directory of your project](project)

## Running the tests

You can test [docker-compose](docker-compose.yml) file by running command
```bash
docker-compose config
```
It must return text of config without errors

## Deployment

**Please note that this project is intended only for development, not for production.**  
I _really_ do not recommend you to running your project with this build in production.

## Built With

* [docker]
* [docker-compose]
* [Phpdocker generator]
* [Nginx] - [alpine version]
* [PHP] - [7.3-fpm version] with Composer 
* [Composer] 
* [ZSH] with [Oh My ZSH!]


[docker]: https://docs.docker.com/install/
[docker-compose]: https://docs.docker.com/compose/install/
[3 or higher]: https://docs.docker.com/compose/compose-file/
[CODESTATS_KEY]: https://codestats.net/my/machines
[Phpdocker generator]: https://phpdocker.io/
[Nginx]: https://nginx.org/
[PHP]: https://www.php.net/
[Composer]: https://getcomposer.org/
[alpine version]: https://hub.docker.com/_/nginx
[7.3-fpm version]: https://hub.docker.com/r/phpdockerio/php73-fpm
[ZSH]: https://www.zsh.org/
[Oh My ZSH!]: https://ohmyz.sh/