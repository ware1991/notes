在資料夾底下創建slim

如果資料夾底下沒有安裝composer 
```
aaa
```

Build slim project
```
php composer.phar create-project slim/slim-skeleton [projectname]
```
move to projct and let php server up
```
cd [project]; php -S 0.0.0.0:8080 -t public public/index.php
```