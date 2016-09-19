在資料夾底下創建slim

如果資料夾底下沒有安裝composer 
```
curl -sS https://getcomposer.org/installer | php
```

Build slim project
```
php composer.phar create-project slim/slim-skeleton [projectname]
```
move to projct and php [server](http://www.slimframework.com/docs/tutorial/first-app.html)
```
cd [project]; php -S 0.0.0.0:8080 -t public public/index.php
```
index.php放在public而不是根目錄的用意
---
讓使用者在存取網頁的時候，只能存取public裡面的資料，而不是整個project的資料都可以存取