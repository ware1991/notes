如果覺得commit 的內容想要修改，可以回到上一步
```
git reset HEAD~
```
就會回到add前的狀態，可以使用status檢查當前狀態

* 監聽log

如果想要看某個檔案是不是有動作，
```
tail -f storage/logs/laravel-2016-10-03.log
```

* [crontab](http://www.nncron.ru/help/EN/working/cron-format.htm)

把預設的editor改成vim，編寫crontab
```
env EDITOR=vim crontab -e
```
然後在檔案裡輸入
```
* * * * * php /home/vagrant/ny-twitter-wall/artisan schedule:run >> /dev/null 2>&1
```
這樣就會每分鐘執行kernel.php裡的schedule
```
$schedule->command('twitter:get')->after(function() { \Log::info('twitter:get work');})->everyMinute();
```