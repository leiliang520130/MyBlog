```php artisan make:migrate create_posts_table
	public function up()
    {
        Schema::create('posts', function (Blueprint $table) {
            $table->increments('id');
            $table->string('title',100)->default("");
            $table->text('content');
            $table->integer('user_id')->default(0);
            $table->timestamps();
        });
    }
public function down()
    {
        Schema::dropIfExists('posts');
    }

```
```php artisan make:migrate chang_img_into_posts
Schema::table('posts', function (Blueprint $table) {
            $table->string('img')->default("")->change()->comment('头像');;
        });

```


