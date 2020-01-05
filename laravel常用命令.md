1.生成api文档
apidoc -i app/Api/Controllers  -o public/apidoc
2.创建控制器
php artisan make:controller PhotoController --resource
3.数据库迁移
php artisan make:migrate create_posts_table
4.所有未完成的迁移
php artisan migrate
5.回滚迁移
php artisan migrate:rollback
6.