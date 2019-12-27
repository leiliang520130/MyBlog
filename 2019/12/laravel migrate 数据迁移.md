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
```language

```


