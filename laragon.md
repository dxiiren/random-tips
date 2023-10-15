Situations :
======

## 1. How to access local host on another PC but on the same wifi ?
* Find pv4 address (in terminal)
```php
ipfoncig
```

* Go to Apache -> httpd.config

![Alt text](<picture/Laragon_Apache.png>)

* Replace with
```php
//FIRST
Listen 0.0.0.0:3000

//SECOND
DocumentRoot "C:/laragon/www/myapp/public"

//THIRD
<Directory "C:/laragon/www/myapp/public">
    Options All
    AllowOverride All
    Require all granted
</Directory>
```

* Run on browser
```php
192.168.8.106:3000
```

## 2. How to do subdomain in virtual server ? 
* Create a config file (right click -> apache -> sites-enabled -> dir)
```php
<VirtualHost *:80> 
    DocumentRoot "C:\laragon\www\kedaiku\public"
    ServerName manage.kedaiku.test
    ServerAlias *.manage.kedaiku.test
    <Directory "C:\laragon\www\kedaiku\public">
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>
```

* Setup driver (right click -> tools -> Edit driver\etc\hosts)
```php
<VirtualHost *:80> 
    127.0.0.1    manage.kedaiku.test
```  

