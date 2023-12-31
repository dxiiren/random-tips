Situations :
======

## 1) Route not found even have run (php artisan route:list)
- you need to run this
```php
php artisan serve optimize:clear
```

## 2. How to access local host on another PC but on the same wifi ?
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

## 3. Artisan shortcut in terminal (php artisan serve to just pas)
* Run this in terminal
```php
notepad $PROFILE
```

* Then write this in notepad and save
```php
function alias { notepad $PROFILE $args }
function pas { php artisan serve $args }
```

* Run this in terminal
```php
pas
```

* if error happen do this
- Open a PowerShell terminal as an administrator
```php
Get-ExecutionPolicy
Set-ExecutionPolicy RemoteSigned
Y
```

## 4. Try these three commands for clearing cache config:

```php
    php artisan config:cache // clear config cache
    php artisan config:clear // clear config cache
    php artisan cache:clear // clear cache
    php artisan optimize  // To reoptimize the class loader
    php artisan route:cache // clear route cache
    php artisan view:clear // clear view cache
```

## 5. How to run 2 artisan command just by using 1 command
* Run this in terminal
```php
notepad $PROFILE
```

* Then write this in notepad and save
```php
function pas2 {
    php artisan optimize:clear
    php artisan serve
}
```

* Run this in terminal
```php
pas2
```

## 6. Pass parameter in artisan command
* Run this in terminal
```php
notepad $PROFILE
```

* Then write this in notepad and save
```php
function pas3 {
    param (
        [string]$hostname
    )

    $command = "php artisan serve --host $hostname --port 3000"
    Invoke-Expression $command
}
```

* Run this in terminal
```php
pas3 -hostname "192.168.8.106"
```