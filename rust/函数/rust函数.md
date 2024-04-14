### 函数
* 声明函数用fn关键字
* 函数命名所有的字母都是小写，单词之间用下划线分开
```rust
		fn main (){
			println!("hello world");
			another_function();
		}
		fn another_function(){
			println!("Another function");
		}
```
* 上面是another_function函数的定义
* 函数的参数
	* 函数的签名里必须声明每一个参数的类型
	* 俩个参数之间用逗号隔开如x: i32, y: i32
```rust
		fn main(){
			another_function(5);
		}
		fn another_function(x: i32){
			println!("the value of x is:{}",x)
		}
```

* 函数体中的语句与表达式：[解释](函数的语句和表达式)
	* 函数体是由一系列的语句组成，可选的由一个表达式结束
	* rust是一个基于表达式的语言
	* 语句是执行一些动作的指令
	* 表达式会计算产生一个值
	* 函数的定义也是一个语句
* 函数的返回值
	* 函数可以返回值，但是返回的值不能命名
	* 要在 -> 后声明函数的返回类型
	* 在rust里函数的返回值就是最后的一个表达式的值
	* 例子如下
```rust
	fn five(x: i32) -> i32 {
		x + 5
	}
	fn main(){
		let x = five(6);
		println("The value of x is {}",x);
	}
```
* 