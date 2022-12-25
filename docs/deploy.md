# Deployment

### Update

```sh
sudo apt update  # This downloads the updates(security, repository links, ...) if any
```

```sh
sudo apt upgrade # Install the updates
```

## [Install PHP7.4](https://www.digitalocean.com/community/tutorials/how-to-install-php-7-4-and-set-up-a-local-development-environment-on-ubuntu-18-04)

```sh
sudo apt -y install software-properties-common
```

```sh
sudo add-apt-repository ppa:ondrej/php
```

```sh
sudo apt-get update
```

```sh
sudo apt -y install php7.4
```

```sh
sudo apt-get install -y php7.4-cli php7.4-json php7.4-common php7.4-mysql php7.4-zip php7.4-gd php7.4-mbstring php7.4-curl php7.4-xml php7.4-bcmath
```

Others:

- https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04

- https://linuxhint.com/install-latest-php-ubuntu22-04/

## Install mysql

```sh
sudo apt install mysql-server
```

```sh
sudo mysql_secure_installation  # setup mysql database server
```

## Installing NodeJs on ubuntu

You can replace 16 with the node version of your choice.

```sh
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash - &&\
sudo apt-get install -y nodejs
```

```sh
sudo npm config set user 0
```

```sh
sudo npm config set unsafe-perm true
```

Link to install NVM: https://tecadmin.net/how-to-install-nvm-on-ubuntu-22-04/

## PM2

## Install a firewall

Research!
Recommendations: ufw
