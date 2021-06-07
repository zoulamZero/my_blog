# 使用各种语言写出hello-world

> ​	事先声明：如果只是hello world的单文件项目，推荐使用vscode的Code Runner插件，安装好编译器就能直接跑了。
>
> ​	现在各种语言也有自己的playground，ts的就很舒服，跑helloworld学语法甚至不需要配置环境了。
>
> 环境默认是`wsl2 + vscode`，推荐观看菜鸟教程安装，本文主要是推荐插件和IDE。
>
> IDE:`Integrated Development Environment`，集成开发环境，就是让你只关心具体代码屏蔽编译过程，提供代码补全、调试、文件跳转等功能的舒适软件。

## IDE

|                                   | IDE                                                        | description                                                  |
| --------------------------------- | ---------------------------------------------------------- | ------------------------------------------------------------ |
| 通用                              | vscode、vim、emacs（基本跟操作系统没啥差别）               | 需要自行配置大量的plugin，vim和emacs需要一定的学习成本       |
| Java                              | IDEA（强烈推荐IDEA）、Notepad++、eclipse                   |                                                              |
| Go                                | GoLand                                                     |                                                              |
| C/Cpp                             | Visual Studio（开发c#也是）                                |                                                              |
| Python                            | Pycharm                                                    | **Jetbrains**家的建议使用高校学生邮箱白嫖，同时可以试试他们家的字体：**JetBrains Mono** |
| Android                           | Android Studio（IDEA社区版改良的）                         |                                                              |
| 前端（JS\|CSS\|HTML及其变种语法） | vscode、webstorm、atom（据说有点卡）、sublime text（收费） | vscode插件安装上就舒服了                                     |
| haskell、rust、php、lisp、ruby    | vscode梭哈                                                 | 如果是 **Jetbrains**粉丝找不到相应的0配置IDE也可以自己找找插件 |

## 源码包类型（以go为例）

| 操作系统 | 源码包                                                       |
| -------- | ------------------------------------------------------------ |
| Windows  | go1.4.windows-amd64.msi     **msi**                          |
| Linux    | go1.4.linux-amd64.tar.gz         **tar.gz**，需要解压        |
| Mac      | go1.4.darwin-amd64-osx10.8.pkg            **mac是基于darwin的** |
| FreeBSD  | go1.4.freebsd-amd64.tar.gz                                   |

```bash
# 解压方式
tar -C <targetPath> -xzf <packageName>
# example
tar -C /usr/local -xzf go1.4.linux-amd64.tar.gz

# 导出环境变量（写入bash.rc始终生效）
export PATH=$PATH:/usr/local/go/bin

# 软连接
ln -s <原始路径> <新路径映射>
# example
ln -s /usr/local/go/bin ~/go
```

## 多版本问题

在linux下可以使用alias（Windows下也应该有alias）对不同版本的编译器添加上不同的别名做出区分，也可以使用版本管理工具：如Node的nvm。

## 编程语言学习问题

自动化脚本：shell、python、nodejs

算法工程师：python实现，cpp提高效率

前端：js或ts，也许也可以是webassembly（cpp or rust）

后端：java、php、go、python、c#

原生：mac（Objective-C），Android（Java、Kotlin）

图形学、操作系统、音视频、高性能软件：c、cpp、rust

## 概念初览

### 环境变量

>  **注：**使用linux发行版自带的软件管理工具：apt-get（Ubuntu）、yum（CentOS）、Arch（pacman），安装不用配置环境变量，安装脚本已经替你完成了。

编译器可以理解为特殊的可执行程序，我们现在的需求是让编译器可以在任何一个文件目录下执行，即需要配置为环境变量。

Windows下：`我的电脑`-> `高级系统设置`-> `环境变量` -> `Path`，点击编辑即可，有两类环境变量，一个是只在当前用户生效和所有用户生效。

​						如果需要复用路径：`%<pathName>%`

Linux（WSL）下：可以使用软链接

### apt-get安装指定版本的软件

```bash
sudo apt-cache madison soft_name
# example
sudo apt-cache madison mysql

# 获取更详细的信息
sudo apt-cache policy soft_name
# example
sudo apt-cache policy mysql
```

### 包管理工具

编程语言一般都会提供包管理工具，包含以下内容：编译、调试的的命令，对应的配置的文件（使用各式语法但是包含基本的本项目信息和依赖名以及版本信息等）。

**注：**通常包的 **默认** 源网站在国外，如果没有翻墙建议使用国内的镜像源。

|        | 包管理工具                     | 配置文件     | 版本锁定文件      | 配置文件语法 |
| ------ | ------------------------------ | ------------ | ----------------- | ------------ |
| Java   | maven、gradle（Android\|Java） | pom.xml      |                   | xml          |
| Node   | npm、yarn                      | package.json | package.lock.json | json         |
| Rust   | cargo                          | Cargo.toml   | Cargo.lock        | toml         |
| python | pip                            |              |                   |              |
| go     |                                |              |                   |              |
|        |                                |              |                   |              |
|        |                                |              |                   |              |

### 学习方式推荐

| 个人情况                                                 | 学习方式推荐                 | 项目                                                         |
| -------------------------------------------------------- | ---------------------------- | ------------------------------------------------------------ |
| 入门                                                     | 看视频                       |                                                              |
| 英语好且有已经有一门熟悉使用的语言，且有一定的计算机基础 | 直接看官网、换语言刷leetcode | github上搜索，xx-awesome，如：go-awesome，找知名的lab自行完成，如cpp的muduo（据说简历上被cpper写烂了） |



## Java

### 安装工具

> JDK、JRE。

### helloworld

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

## Golang



## Node

> 推荐工具nvm，进行Node的版本管理。
>
> Windows下是 [nvm-windows](https://github.com/coreybutler/nvm-windows)

```javascript
console.log('hello world')
process.stdout.write('hello world')
```

## cpp

## python(3)

```python
print('Hello World!')
```

## rust

