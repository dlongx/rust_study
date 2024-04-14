# 基础指令
## cargo run
* 先编译(为二进制)后执行
* 若之前编译成功过却源代码没有改变则会直接运行二进制文件
* 相当于先cargo build 编译在运行文件
## cargo builed（构建cargo项目）
* 创建可执行文件：在`target/debug/[项目名]或者target\debug\[项目名](win下)`
* 也可运行该文件：`./`target/debug/[项目名]或者.\target\debug\[项目名]`
* 运行cargo builed则会在项目目录下生成cargo.lock文件该文件包含项目的依赖的精确版本
* cargo build --release(为发布构建)
	* 编译时对代码进行优化，代码运行的会更快，但是编译时间更长
	* 可执行文件生成在target/release而不是target/debug下
## cargo check
* 检查代码，不产生任何可执行文件
* check比builed快，在编写的时候可以反复使用cargo check检查代码