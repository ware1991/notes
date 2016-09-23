#使用twitter API自動抓取使用者的tweet

First step
---
到要放project的地方將project clone下來，
```
git clone https://github.com/ware1991/NY-Twitter-Wall.git
```
每次將project clone下來的第一件事情，就是將專案會用到的插件先安裝好
```
composer install
```
Second step
----
安裝完後，確認git狀態
```
git init
```
```
git status
```
創建一個新的branch，以區分上傳的功能，
```
git checkout -b feature/getUserTimeLine
```
Third step
---
安裝homestead
```
composer require laravel/homestead -dev
```
homestead.phar
```
php vendor/bin/homestead make
```
4st
---
啟用 vagrant
```
vagrant up
```
進入 vagrant
```
vagrant ssh
```
如果還沒把資料庫建起來，就進入mysql創建一個for專案的資料庫
```
mysql -uhomestead -psecret
```
```
CREAT TABLE twitterWall
```
記得將homestead.ymal裡的IP改成和sequel pro的ip一樣
EX:192.168.10.10
5st
---
部署migration
創建功能所需的table，命名規則採用snake case，如creat_[table_names]_talbe，記得tablename要加s
```
php artisan make:migration create_wall_infomations_table --create="wall_infomations"
```
將Table的Schema寫好後，執行migrate
```
php artisan migrate
```
執行完後檢查資料庫，是否有成功創建table，如果成功創建後，執行migrate:rollback
```
php artisan migrate:rollback
```
創建跟migration連結的model
```
php artisan make:model WallInfomation
```





###@@@如果專案不是自己本地new的，就要下指令來產生新的APP_KEY，
```
＄    php artisan key:generate
```







