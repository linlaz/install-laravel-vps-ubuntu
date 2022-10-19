# install-laravel-vps-ubuntu
## Instalasi

- update
```
sudo apt update
sudo apt upgrade
```

- install apache2
```
sudo apt-get install apache2
sudo systemctl status apache2
```

- Install php
```
sudo apt-get install php libapache2-mod-php php-common php-gmp php-mbstring php-xmlrpc php-soap php-gd php-xml php-cli php-zip php-bcmath php-tokenizer php-json php-pear php-intl php-curl php-mysql
sudo apt-get update
```

- Install Curl
```
sudo apt-get install curl
```

- Install composer
```
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer
composer -v
```

- Install nodejs
```
curl -sL https://deb.nodesource.com/setup_14.x | sudo -E bash -
sudo apt-get install -y nodejs
node -v
npm -v
```

- Install mysql-server
```
sudo apt-get install mysql-server
```

- login mysql server using root
```
sudo mysql -u root -p
```

- Update password & Create Database
```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'bagisto';
create database bagisto;
exit;
```

- Create Project Using Composer
```
composer create-project bagisto/bagisto
```

- Setting apache2 
```
sudo nano /etc/apache2/apache2.conf
```

- Add in Directory 
```
<Directory /home/<nameuser>/bagisto/public>
        Options FollowSymLinks
        AllowOverride All
        Require all granted
</Directory>
```

- Update default sites available
```
DocumentRoot /home/<nameuser>/bagisto/public
```

- Setting Permission
```
sudo chmod -R 755 /home/lazuardilintang/bagisto
sudo chown -R www-data /home/lazuardilintang/bagisto
```

- Enable rewrite
```
sudo a2enmod rewrite
```

- Restart apache2
```
sudo systemctl restart apache2.service
```


