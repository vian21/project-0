# Deployment

### Update
```sh
sudo apt update  # This downloads the updates(security, repository links, ...) if any
```
```sh
sudo apt upgrade # Install the updates
```
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
## PM2

## Install a firewall
Research! 
Recommendations: ufw