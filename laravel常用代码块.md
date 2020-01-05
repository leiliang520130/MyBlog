1.原来在model层getNameAttribute()方法里，对从数据库取出的name字段做了处理
```public function getNameAttribute($value){
    if(!is_array($value)) $value = json_decode($value, true);
    return $value;
}

```

