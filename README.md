# Laravel on Ubuntu 20.04

install : git, composer, virtualbox, vagrant, heidisql

composer global require laravel/installer

git clone https://github.com/jiehoes/lvtofossa.git

cd lvtofossa

composer install

vagrant up

composer install

create database XXXXXX-0X

copy jiholaravelfocalfossa2.box into directory

vagrant box add jiholaravelfocalfossa2 jiholaravelfocalfossa2.box

vagrant up

### Database

vagrant ssh
$ sudo mysql -u root --password='root' < /var/www/html/database.sql
$ exit

open heidisql: 192.168.XX.XX; root P3rtamax

or advanced:
php artisan storage:fresh

### Create symlink

php artisan storage:link

browse http://192.168.XX.XX

### Configuration

sudo nano /etc/apache2/conf-enabled/serve-cgi-bin.conf

    ScriptAlias /cgi-bin/ /usr/lib/cgi-bin/

    <Directory "/usr/lib/cgi-bin/">

    AllowOverride All

    Options +ExecCGI -MultiViews +FollowSymLinks

    AddHandler fcgid-script .fcgi

    Require all granted

    </Directory>
