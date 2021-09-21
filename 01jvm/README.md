# 第1周作业

## 作业内容

### Week01 作业题目：

1.（选做）自己写一个简单的 Hello.java，里面需要涉及基本类型，四则运行，if 和 for，然后自己分析一下对应的字节码，有问题群里讨论。

2.（必做）自定义一个 Classloader，加载一个 Hello.xlass 文件，执行 hello 方法，此文件内容是一个 Hello.class 文件所有字节（x=255-x）处理后的文件。文件群里提供。

3.（必做）画一张图，展示 Xmx、Xms、Xmn、Meta、DirectMemory、Xss 这些内存参数的关系。

4.（选做）检查一下自己维护的业务系统的 JVM 参数配置，用 jstat 和 jstack、jmap 查看一下详情，并且自己独立分析一下大概情况，思考有没有不合理的地方，如何改进。

注意：如果没有线上系统，可以自己 run 一个 web/java 项目。

5.（选做）本机使用 G1 GC 启动一个程序，仿照课上案例分析一下 JVM 情况。

### 作业1（选做）

1. 编写代码, Hello.java

2. 编译代码, 执行命令： javac -g Hello.java
   > 注意：怎么处理警告:编码 GBK 的不可映射字符
   > 
   > 输入javac  -encoding utf-8  文件名.java。就可以解决了。 
   > 
   > 当Java源代码中包含中文字符时，我们在用javac编译时会出现“错误：编码GBK的不可映射字符”。
   >
   > 由于JDK是国际版的，我们在用javac编译时，编译程序首先会获得我们操作系统默认采用的编码格式（GBK），然后JDK就把Java源文件从GBK编码格式转换为Java内部默认的Unicode格式放入内存中，然后javac把转换后的Unicode格式的文件编译成class类文件。
   > 此时，class文件是Unicode编码的，它暂存在内存中，紧接着，JDK将此以Unicode格式编码的class文件保存到操作系统中形成我们见到的class文件。
   > 
   > 当我们不加设置就编译时，相当于使用了参数：javac -encoding GBK Test.java，就会出现不兼容的情况。

3. 查看反编译的代码。

- 3.1 可以安装并使用idea的jclasslib插件, 选中 Hello.java 文件, 选择 ` View --> Show Bytecode With jclasslib ` 即可。 

- 3.2 或者直接通过命令行工具 javap, 执行命令: ` javap -v Hello.class ` 

4. 分析相关的字节码。
