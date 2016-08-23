# js-arguments
js中arguments用法

返回一个 arguments 对象中的各个参数的实际值，相应的值是由一个正在执行的函数的 arguments 属性返回的。
例如
```javascript
function add(a,b,c){
	var sum=a+b+c;
	console.log(arguments)//[10, 20, 30],返回正在执行的（这里指的是参数为10,20,30的这个函数传入的参数）
	console.log(arguments[0])//10
	console.log(arguments[1])//20
	console.log(arguments[2])//30
	console.log(arguments.length)//3 返回参数的个数
	return sum;
}
add(10,20,30)
```

例二
```javascript
function add(a,b,c){
	var sum=a+b+c;
	console.log(arguments)//[10, 20, 30],但是它不是数组
	console.log(arguments[0])//10
	console.log(arguments[1])//20
	console.log(arguments[2])//30
	return sum;
}
add(10,20,30)
add(40,50,60)
/*---------------------------------*/
//控制台返回的值
[10, 20, 30]
10
20
30
[40, 50, 60]
40
50
60

```
我们发现arguments的值并没有被覆盖，这就是重载


<h3>arguments的callee属性<h3>
表示对函数对象本身的引用，也就是所指定的 Function 对象的正文，这有利于实现匿名函数的递归或者保证函数的封装性。<br>
example<br>
用递归来计算1到n的自然数之和：
```javascript
<script>
   var sum=function(n){
　   if(1==n) {
       return 1;
　   } else {
       return n + arguments.callee(n-1);
     }
　 }
　 alert(sum(100));
</script>
```

