## 01-二进制：了解计算机的源头



### 1 什么是二进制计数法？

人类计数的发展史：

1. 原始时代，路边小石子统计放牧羊的数量；

2. 罗马人，用手指计数，在羊皮上画**I**、**II**、**III**来替代手指数量，**V**来表示一只手，**VV**表示两只手；

3. 公元3世纪左右，印度数学家（或是阿拉伯人）发明阿拉伯数字，并采用**进位制法**；

4. 以阿拉伯数字为基础，产生了**十进制计数法**；

   ![](/Users/andyron/myfield/github/LearnMath/images/mathfp-002.jpg)

   其中 **^** 表示幂或次方运算。十进制的数位（千位、百位、十位等）全部都是10^n的形式。10被称为十进制计数法的**基数**。

5. 类比，**二进制的数位就是2^n的形式**；

   ![](/Users/andyron/myfield/github/LearnMath/images/mathfp-003.jpg)

6. 同样，也可以推导产生**八进制**、**十六进制**等等计数法；



### 2 计算机为什么使用二进制？

计算机使用二进制和现代计算机系统的**硬件实现**有关。组成计算机系统的逻辑电路通常只有两个状态，即开关的**接通**与**断开**，分别可用1、0表示。只有两种状态，即便系统受到干扰，也能分辨出来，因此使用二进制具有**抗干扰能力强、可靠性高**的优点。相比之下，如果用十进制设计具有 10 种状态的电路，情况就会会非常复杂，判断状态的时候出错的几率就会大大提高。

另外，**二进制也非常适合逻辑运算**。



### 3 二进制的位操作/位运算

#### 3.1 向左移位

![](/Users/andyron/myfield/github/LearnMath/images/mathfp-004.jpg)

**二进制左移一位，其实就是将数字翻倍**。`110101 (53)` 向左移一位变成`1101010(106)`

向左移位需要注意**数字溢出**，也就是二进制位数超过了系统指定的位数（目前一般是32位或64位）。

#### 3.2 向右移位

![](/Users/andyron/myfield/github/LearnMath/images/mathfp-005.jpg)

**二进制右移一位，就是将数字除以 2 并求整数商的操作**。

#### 位的“或”

![](/Users/andyron/myfield/github/LearnMath/images/mathfp-006.jpg)

#### 位的“与”

![](/Users/andyron/myfield/github/LearnMath/images/mathfp-007.jpg)

#### 位的“异或”

![](/Users/andyron/myfield/github/LearnMath/images/mathfp-008.jpg)



## 02-余数：原来取余操作本身就是个哈希函数

**同余定理**：两个正整数a和b，如果它们除以正整数m得到的余数相等，就认为a和b对于**模m**同余。示例：

100天里，所有星期一的这些天都是同余的；

![](/Users/andyron/myfield/github/LearnMath/images/mathfp-009.jpg)

奇数和偶数，可以看作是模为2的同余应用；

...



整数是没有边界的，它可能是正无穷，也可能是负无穷。**余数总是在一个固定的范围内**(0~m，不包括m)。同余定理就可以**用来均分**了。

哈希（Hash，散列）就是**将任意长度的输入，通过哈希算法，压缩为某一固定长度的输出**。



![](/Users/andyron/myfield/github/LearnMath/images/mathfp-010.jpg)



![](/Users/andyron/myfield/github/LearnMath/images/mathfp-010.jpg)





![](/Users/andyron/myfield/github/LearnMath/images/mathfp-012.jpg)



![](/Users/andyron/myfield/github/LearnMath/images/mathfp-013.jpg)



#### 使用余数思想的例子

循环冗余校验，[最大公约数](https://baike.baidu.com/item/最大公约数/869308?fr=aladdin)，[模幂运算](https://baike.baidu.com/item/蒙哥马利幂模运算/10566438?fr=aladdin&fromid=16255096&fromtitle=模幂运算)(DES、AES、RSA)，[凯撒密码](https://baike.baidu.com/item/恺撒密码/4905284?fromtitle=凯撒密码&fromid=1336345&fr=aladdin)，[孙子定理](https://baike.baidu.com/item/孙子定理/2841597?fr=aladdin)，[水仙花数](https://baike.baidu.com/item/水仙花数/2746160?fr=aladdin)，闰年的计算都是以模运算为基础的。