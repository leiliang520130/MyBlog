$redis = new Redis();
$redis->connect('127.0.0.1',6379);

$redis->watch('sale');

$sales = $redis->get('sale');

$store = 10;

if($sales>=$store){
	exit("")
}