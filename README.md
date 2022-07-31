# Docker-Opencart-Mariadb(Mysql)-Phpmyadmin

## How to start?

- Clone repository to `your-opencart-folder`

- Download [opencart package](https://www.opencart.com/index.php?route=cms/download/history), extract then copy `~/downloaded-opencart/upload` to `your-opencart-folder/src`

- Run `docker-compose build && docker-compose up -d`

- When loady your store in the first time, try enter needed informations

- Make sure the Hostname is **`mariadb`** or **`mysql`** (this is the service name of mariadb or mysql in `docker-compose.yml`)

- Rename `./src/config-dist.php` to `./src/config.php`

- Rename `./src/amdin/config-dist.php` to `./src/admin/config.php`

- Click Next

- Remove `./src/install` folder

- Enjoy!

## Directory structure

- Refer [folder-constructe.png](https://github.com/thuydtshop/Docker-Opencart-Mariadb-Mysql-Phpmyadmin/blob/main/folder-constructe.png)

## Database config

- You can change databse name, database user, database password, database root password in `docker-compose.yml`

- Other way, try create `.env` then put database information there

## How to change `storage` folder?

- Open line `'./storage:/var/www/storage'` in `docker-compose.yml`

- Comment line of code `$json['error'] = $this->language->get('error_admin_exists');` in `./src/admin/controller/common`

- Login to `admin` again then do change `storage` to `new-path` (make sure same path which you have configured in `docker-compose.yml`)

- Build && up container

## How to change `admin` folder?

- Open line `./src/admin/:/var/www/html/adminXXX/` in `docker-compose.yml`

- Open line `COPY ./src/admin /var/www/html/adminXXX` in `.docker/Dockerfile` (make sure same path which you have configured in `docker-compose.yml`)

- Comment line of code `$json['error'] = $this->language->get('error_admin_exists');` in `./src/admin/controller/common`

- Build && up container

- Login to `admin` again then do change `admin` to `adminXXX`

- Refresh admin page again

## References

- Opencart

- Docker
