###first step : 
將資料庫必須欄位建立起來

###second step：
解析資料表欄位，並輸入

###third step：
將資料顯示在頁面上

##錯誤紀錄
要記得將autoload拉進來
```
composer dump-autoload -o
```
要記得先將league/csv拉進來
```
composer require league/csv
```

<?php
require_once __DIR__ . 'Vendor/autoload.php';

use League/Csv/Reader;

try {

 //P20160830-098,好漾旅行社,Facebook粉絲讚,20000,0,1000,21000,,,列標籤,加總 / 廣告費用(NTD) // ['P20160830-098', '好漾旅行社', 'Facebook粉絲讚'] $row1 = $csv->fetchOne();

 $pdo = new PDO('mysql:host = 192.168.10.90;dbname =ricky','homestead','secret');

 $csv = Reader::createFromPath('/Users/ricky/projects/homestead.csv');

 //get the first row, usually the CSV header $headers = $csv->fetchOne();

 //get rows without header, usually the CSV content $res = $csv->setOffset(1);

 $sth = $dbh->prepare( "INSERT INTO ricky (projectnum, user, method, charge, fee, tax, subtotal)  VALUES (:projectnum, :user, :method, :charge, :fee, :tax, :subtotal)" );

 $orderInser = $csv->each(function ($row) use (&$sth) { //Do not forget to validate your data before inserting it in your database $sth->bindValue(':projectnum', $row[0], PDO::PARAM_STR); $sth->bindValue(':user', $row[1], PDO::PARAM_STR); $sth->bindValue(':method', $row[2], PDO::PARAM_STR); $sth->bindValue(':charge', $row[3], PDO::PARAM_STR); $sth->bindValue(':fee', $row[4], PDO::PARAM_STR); $sth->bindValue(':tax', $row[5], PDO::PARAM_STR); $sth->bindValue(':subtotal', $row[6], PDO::PARAM_STR);

 return $sth->execute();

} catch (PDOException $e) {

 die('Could not connect');

}

echo $row1;

// $results = $sth ->fetchAll(PDO::FETCH_OBJ);

// var_dump($results);
