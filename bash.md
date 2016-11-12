first shell script
```
vim [filename].sh
```
run shell script
```
./[filename].sh
```
SHELL脚本一般都会加 #!/usr/bin/bash，如果你使用其他的SHELL，也有各种情况：如：#!/bin/sh#!/bin/ksh#!/usr/bin/php

practice in terminal
```
date
```
```
date | awk '{print $1 " " $2}'
```

快速搜尋檔案
```
ls -l {w*,*oo*}
```
```
目前失敗，但確定可以程式碼無誤
ls -l [fw]*
ls -l [e-q]*
```
找出錯誤碼 in terminal
```
sh -x first.sh
```