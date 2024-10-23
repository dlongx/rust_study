1:在Rust中，类似{/* .. * /} 的大括号块是:（）多选
A.一个表达式
B.一个语句
C.一个语法作用域
答案：AC
理解：A:/ * .. * /是一个块注释在{}中不占意思则就如同main函数中最后一个表达式是()一样{/* .. * /}也是一个表达式，返回了一个()值
C:如下
```rust
fn main() {  
    println!("Hello, world!");  
    another_function();  
}  
fn another_function(){ 
	let x = 1；
    println!("Another function.");  
}
```
x的作用域只在another_function函数中用{}包裹着所以{/* .. * /}也是一个语法作用域
 ······ 
 2.以下代码能否通过编译?如果能，那输出多少?
 ```rust
 fn f(x:i32)->i32{x+ 1 }
 fn main(){
	 println!("{}"，f({
		 let y= 1;
		 y + 1
	}));
}
```
这样看稍显复杂一步步来
如下
```rust
fn f(x:i32)->i32 {x+ 1 }
fn main(){println!("{}"，f({let y= 1;y + 1}));}
//先看main函数打印f则
println!("{}"，f({let y= 1;y + 1}))
|下一步
f({let y= 1;y + 1})
|定义了一个y，{let y= 1;y + 1}这个表达式的返回值是2则f函数的参数是2
fn f(x:i32)->i32 {x+ 1 }
|这样f函数的返回值是3
fn main(){println!("{}"，f)}
|所以整体的输出是3
```