Situations :
======


## 1. How to access local host on another PC but on the same wifi ?
* Find pv4 address (in terminal)
```php
ipfoncig
```

* Run Artisan Command
```php
php artisan serve --host 192.168.8.106 --port 3000
```

* Run on browser
```php
192.168.8.106:3000
```

## 2. Artisan shortcut in terminal (php artisan serve to just pas)
*Run this in terminal
```php
notepad $PROFILE
```

*Then write this in notepad and save
```php
function pas { php artisan serve $args }
```

*if error happen do this
- Open a PowerShell terminal as an administrator
```php
Get-ExecutionPolicy
Set-ExecutionPolicy RemoteSigned
Y
```


