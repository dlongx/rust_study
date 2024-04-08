* 下面是用match语句重写if-else链来处理多个判断
```rust
fn main() {
    let number: i32 = 6;
  
    if number % 4 == 0{
        println!("number is divisible by 4");
    }else if number % 3 == 0{
        println!("number is divisible by 3");
    }else if number % 2 == 0{
        println!("number is divisible by 2");
    }else{
        println!("number is not divisible by 4, 3 or 2")
    }
 }
```
* 下面的并没有包含全部情况
```rust
fn main() {
    let number: i32 = 6;
    
    match (number % 4 == 0, number % 3 == 0, number % 2 == 0) {
        (true, _, _) => println!("number is divisible by 4"),
        (_, true, _) => println!("number is divisible by 3"),
        (_, _, true) => println!("number is divisible by 2"),
        _ => println!("number is not divisible by 4, 3, or 2"),
    }
}
```
* 当同时满足两个条件时
```rust
fn main() {

    let number: i32 = 6;

    match (number % 4 == 0, number % 3 == 0, number % 2 == 0) {
        (true, _, true) => println!("number is divisible by both 4 and 2"),
        // 检查是否同时被3和2整除
        (_, true, true) => println!("number is divisible by both 3 and 2"),
        // 单独的条件检查
        (true, _, _) => println!("number is divisible by 4"),
        (_, true, _) => println!("number is divisible by 3"),
        (_, _, true) => println!("number is divisible by 2"),
        _ => println!("number is not divisible by 4, 3, or 2"),
    }
}
```