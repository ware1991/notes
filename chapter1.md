# **build new laravel project**

first step:

到使用者底下 cd ~ : 
```
cd ~/
```

創建一個新的資料夾mkdir \[filename\] : 
```
mkdir project
```
到新的資料夾底下建立一個laravel專案laravel new \[projectname\]：
```
laravel new first
```
@建立一個軟連結for快速開啟sublime text 
```
ln -s "/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" ~/bin/subl
```
專案創建完後require laravel進來：composer require 
```
composer require laravel/homestead
```
建立需要的資料：
```
php vendor/bin/homestead make
```
以上動作執行完後就可以開始編輯laravel：因為已經建立軟連結，所以只要輸入「subl .」就可以利用sublime text 開啟整個專案，記得subl 後面要空格然後一點



# Laravel Project with valet

install php70 or new version : brew install php70 --without-apach

new a folder for valet &do comment in this folder：composer global require laravel\/valet

@make sure you had write """export PATH=~\/.composer\/vendor\/bin:$PATH""" into ~\/.bash\_profile

run commend in folder：valet install  

next ：valet park

new a laravel project：laravel new vala

then you can run laravel in browser  http:\/\/\[project name\].dev：http:\/\/vala.dev



