Situations :
======


## 1. How to acess local host on another PC but on the same wifi ?
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


