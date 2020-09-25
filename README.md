# Laravel on Ubuntu 20.04

install : git, composer, virtualbox, vagrant, heidisql

composer global require laravel/installer

git clone https://github.com/jiehoes/lvtofossa.git

cd lvtofossa

composer install

.vagrantfile set IP to: 192.168.56.30

.env set to: DB_HOST=192.168.56.30

vagrant up

vagrant ssh

    $ sudo mysql -u root --password='root' < /var/www/html/database.sql

    $ exit

### heidisql

host:192.168.56.30 user:root pass:root

php artisan migrate

see http://192.168.56.30

### Configuration

sudo nano /etc/apache2/conf-enabled/serve-cgi-bin.conf

    ScriptAlias /cgi-bin/ /usr/lib/cgi-bin/

    <Directory "/usr/lib/cgi-bin/">

    AllowOverride All

    Options +ExecCGI -MultiViews +FollowSymLinks

    AddHandler fcgid-script .fcgi

    Require all granted

    </Directory>
