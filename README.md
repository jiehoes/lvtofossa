# Laravel on Ubuntu 20.04

requirement : git, composer, virtualbox, vagrant, heidisql

    composer global require laravel/installer

    git clone https://github.com/jiehoes/lvtofossa.git

    cd lvtofossa

    composer install

.vagrantfile set IP to: 192.168.56.30

.env set to: DB_HOST=192.168.56.30

    vagrant up

    vagrant ssh

### heidisql

create new session host:192.168.56.30 user:root pass:root

    php artisan migrate

### environment

    DB_CONNECTION=mysql

    DB_HOST=192.168.56.30

    DB_PORT=3306

    DB_DATABASE=laravel

    DB_USERNAME=root

    DB_PASSWORD=root

### mapserver

we've modified this:

sudo nano /etc/apache2/conf-enabled/serve-cgi-bin.conf

    ScriptAlias /cgi-bin/ /usr/lib/cgi-bin/

    <Directory "/usr/lib/cgi-bin/">

    AllowOverride All

    Options +ExecCGI -MultiViews +FollowSymLinks

    AddHandler fcgid-script .fcgi

    Require all granted

    </Directory>

see http://192.168.56.30

see http://192.168.56.30/cgi-bin/mapserv?

![Virtualbox](network.png)


### v1.0.1

Windows: C:\Windows\System32\drivers\etc\hosts

    192.168.56.30   lvtofossa-laravel8-01.vagrant

see http://lvtofossa-laravel8-01.vagrant

see http://lvtofossa-laravel8-01.vagrant/cgi-bin/mapserv?

