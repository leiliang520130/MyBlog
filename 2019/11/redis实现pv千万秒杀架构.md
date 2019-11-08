$redis = new Redis();
$redis->connect('127.0.0.1',6379);

$redis->watch('sale');

$sales = $redis->get('sale');

$store = 10;

if($sales>=$store){
	exit("活动结束");
}

$redis->multi();
$redis->incr('sale');
$res = $redis->exec();
if($res){
	//扣库存
}else{
	//秒杀失败
}