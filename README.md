#    Python学习笔记

## 安装python

### 使用anoconda管理python版本

**为什么使用要进行版本管理？**

> python的版本管理问题一直是很令人头疼，因为使用python时可能需要针对工作的环境下载不同的依赖包，配置适合某个版本的整体的依赖包，例如说进行图像处理学习的整个依赖环境、进行深度学习的整个依赖环境。
>
> 使用anoconda管理python和依赖包可以达到便捷的目的。

**创建一个使用anaconda的python工程**

我们需要在pycharm中创建一个基于anoconda环境的工程，在创建时就可以选择对应的python版本，同时项目创建完成时会在 *D:\Environment\anaconda\envs（我此时anaconda的根目录下的envs）* 目录下创建一个与工程同名的文件夹用于存储完整的环境依赖。

<p align="center"><img src="https://gitee.com/aiyudehua/drawing-bed/raw/master/https://gitee.com/aiyudehua/drawing-bed/tree/master/img/image-20210623230555160.png" /> </p>
<p align="center">创建一个包含完整依赖包的工程</p>

**查看anaconda所有已创建的环境**

```shell
conda info -e # 控制台下
```

<p align="center"><img src="https://gitee.com/aiyudehua/drawing-bed/raw/master/https://gitee.com/aiyudehua/drawing-bed/tree/master/img/image-20210623231759367.png" /> </p>
<p align="center">查看已创建的环境</p>

**激活环境**

```python
activate 工程名
# 例 activate Test
```

**安装只属于此环境的依赖包**

进入新创建的环境后我们可以使用pip工具安装只属于此环境的依赖包

①使用离线文件(如.whl)安装

```shell
pip install 文件全路径 # 可以将文件拖入控制台
```

②在线安装(无翻墙情况下很慢)

```shell
pip install numpy==1.18.5	# 指定安装包的版本
```

**python依赖包的获取网址**

python使用pip工具进行包管理，有时候需要下载离线包，可以从pypi网址上搜索各个版本的安装包。

https://pypi.org/

<p align="center"><img src="https://gitee.com/aiyudehua/drawing-bed/raw/master/https://gitee.com/aiyudehua/drawing-bed/tree/master/img/image-20210623225706899.png" /> </p>
<p align="center">pypi</p>

## 语言元素

### if语句的使用

在Python中，要构造分支结构可以使用`if`、`elif`和`else`关键字。所谓**关键字**就是有特殊含义的单词，像`if`和`else`就是专门用于构造分支结构的关键字，很显然你不能够使用它作为变量名（事实上，用作其他的标识符也是不可以）。下面的例子中演示了如何构造一个分支结构。

```Python
"""
用户身份验证
"""
username = input('请输入用户名: ')
password = input('请输入口令: ')
# 用户名是admin且密码是123456则身份验证成功否则身份验证失败
if username == 'admin' and password == '123456':
    print('身份验证成功!')
else:
    print('身份验证失败!')
```

需要说明的是和C/C++、Java等语言不同，Python中没有用花括号来构造代码块而是**使用了缩进的方式来表示代码的层次结构**，如果`if`条件成立的情况下需要执行多条语句，只要保持多条语句具有相同的缩进就可以了。换句话说**连续的代码如果又保持了相同的缩进那么它们属于同一个代码块**，相当于是一个执行的整体。**缩进**可以使用任意数量的空格，但**通常使用4个空格**，建议大家**不要使用制表键**或者**设置你的代码编辑工具自动将制表键变成4个空格**。

### 运算符

Python支持多种运算符，下表大致按照优先级从高到低的顺序列出了所有的运算符，运算符的优先级指的是多个运算符同时出现时，先做什么运算然后再做什么运算。

| 运算符                                                       | 描述                           |
| ------------------------------------------------------------ | ------------------------------ |
| `[]` `[:]`                                                   | 下标，切片                     |
| `**`                                                         | 指数                           |
| `~` `+` `-`                                                  | 按位取反, 正负号               |
| `*` `/` `%` `//`                                             | 乘，除，模，整除               |
| `+` `-`                                                      | 加，减                         |
| `>>` `<<`                                                    | 右移，左移                     |
| `&`                                                          | 按位与                         |
| `^` `\|`                                                     | 按位异或，按位或               |
| `<=` `<` `>` `>=`                                            | 小于等于，小于，大于，大于等于 |
| `==` `!=`                                                    | 等于，不等于                   |
| `is`  `is not`                                               | 身份运算符                     |
| `in` `not in`                                                | 成员运算符                     |
| `not` `or` `and`                                             | 逻辑运算符                     |
| `=` `+=` `-=` `*=` `/=` `%=` `//=` `**=` `&=` `|=` `^=` `>>=` `<<=` | （复合）赋值运算符             |

>**说明：** 在实际开发中，如果搞不清楚运算符的优先级，可以使用括号来确保运算的执行顺序。

学习