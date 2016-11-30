安裝homestead
```
composer require laravel/homestead
```
make 指令將會自動配置 sites 及 folders 於 Homestead.yaml
```
php vendor/bin/homestead make
```

更改homestead.yaml裡的
- folders: 要引入的資料夾
- sites: 設定APP路徑


進入vagrant後
更改設定檔
```
/etc/nginx/sites-available
```


homestead.yaml範例
```
---ip: "192.168.33.88"memory: 2048cpus: 1hostname: homesteadname: erpprovider: virtualbox

authorize: ~/.ssh/id_rsa.pub

keys: - ~/.ssh/id_rsa

folders: - map: "/Users/ricky/erp-projects" to: "/home/vagrant/apps"

sites: - map: erp.app to: "/home/vagrant/apps/erp/public" - map: partner.app to: "/home/vagrant/apps/partner/public"

databases: - homestead
```