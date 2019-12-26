strict_types指令
declare(strict_types=1);
默认情况下，所有的 PHP 文件都处于弱类型校验模式。新的 declare 指令，通过指定 strict_types 的值（1 或者 0），1 表示严格类型校验模式，作用于函数调用和返回语句；0 表示弱类型校验模式。
declare (strict_types=1) 必须是文件的第一个语句。如果这个语句出现在文件的其他地方，将会产生一个编译错误，块模式是被明确禁止的。
类似于 encoding 指令，但不同于 ticks 指令，strict_types 指令只影响指定使用的文件，不会影响被它包含（通过 include 等方式）进来的其他文件。该指令在运行时编译，不能修改。它的运作方式，是在 opcode 中设置一个标志位，让函数调用和返回类型检查符合类型约束。

```php
declare(strict_types=1);
 
function func(int $num): int {
    return $num;
}
var_dump(func(2)); // returned value：int(2)

declare(strict_types=1);
 
function func($num):int{
    return $num;
}
var_dump(func(2.5)); // returned value：Return value of func() must be of the type integer, float returned

```

