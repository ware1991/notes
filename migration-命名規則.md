創建一個migration時，遵照一些命名規則，可以讓下一個使用者，更容易懂這個migration是做何用途，例如創建table就可以採用creat_[table_names]_table。

記得migration命名規則採用snake case,且table name後面一定要有s
```
art make:migration create_wall_infomations_table --create="wall_infomations"
```
如果遵照創建migration有遵照snake case，在創建model的時候就可以，就可以不用特地使用public。

記得model命名規則採用camel case，並且使用table_name
```
php artisan make:model WallInfomation
```