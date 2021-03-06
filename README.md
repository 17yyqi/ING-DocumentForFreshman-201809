# 数模组新人指南
## 公共讨论区，在文档还没有发布之前在这里讨论相关问题
&emsp;&emsp;编程语言是不是应该在常用软件里面单独地列出一类呢？ 感觉这个东西直接放到应用软件里面讨论，可能会有一些问题，可以在应用软件里面讨论软件的
IDE及可能需要的编译器会好一些
## 编写这个文档可能需要注意的语法问题
```
#### XXX    
由于GitHub的一些特性 请在#后面加入空格，保证其标题的效果会显现    
&emsp;    
表示全角空格，可以在段首加入，以保证其缩进
如果需要贴图，可以看到仓库下面有Picture文件夹，上传到这里，然后利用markdown语法贴链接就行
如果是网络图片，那就直接贴链接（当然年头久了外链可能失效）
```
## 介绍及版权说明
&emsp;&emsp;数模组新生入门手册——长期维护> &lt;（使用GPL许可证  非商用授权 如果使用其中内容请表明出处）  
## 一、常用软件工具及基本配置方法（日常生活学习用）
### 1 系统软件
* 可以尝试安装archlinux系统来体验自定义安装操作系统的感觉。为什么是archlinux呢？原因如下:
	* 我们安装windows都是被引导着被动下一步，失去了自己给磁盘分区，设置引导，连接网络，安装自己喜欢的桌面环境等等很多过程。arch自由度比较高。
	* arhlinux滚动更新。
	* 可以使用pacman安装很多软件，只要mirrorlist里面有，pacman帮我们找到软件来源，用户只需要告诉他匹配的名字就好了。
* 挂载双系统：可以用grub挂载双系统．第二个系统和第一个系统共用EFI分区，这样就不用每次都进入Boot选择进入那个分区了。
 
### 2 应用软件

好的软件可以帮助我们提高办公学习效率以及编写代码的体验。

* python——可以用Anaconda管理，IPython+JupiterNoteBook。


## 二、数学建模常用的两大软件Matlab与Latex的简单介绍及入门
### 1. Matlab

### 2 Latex基础入门
#### 1 基本格式
* 文档的开始和结束
```
\documentclass[12pt]{ctexart}
\usepackage{graphicx}  %这里主要是插入一些宏包
\begin{document}
\section{1}
\subsection{123}
一些内容
\end{document}
```
* 一二三级标题
```
\section{}      %一级标题
\subsection{}   %二级标题
\subsubsection{}%三级标题
```
通常在中文论文写作中，一级标题用汉字书写，只需要添加一行
```
\CTEXsetup[number={\chinese{section}}]{section}
```
* 注释
	* 单行注释使用%
	* 多行注释
	```
	\usepackage{verbatim}
	\begin{comment}
	
	\end{comment}
	```
#### 2 插入图片
```
\usepackage{graphicx}
\begin{figure}[!h]
  \centering
   \includegraphics[width=0.8\textwidth]{picture.jpg}
  \caption{图片}
\end{figure}
```
需要注意的是，picture.jpg应与.tex处于同一目录下。同时，对于一些复杂格式的图片不能采用此方式保存。
#### 3 数学公式
* 公式语法
	* 下标使用_{下标内容}，上标使用^{上标内容}
	* 分式使用\dfrac{分子}{分母}
	* 希腊字母如β使用\beta
* 插入公式
	* 不换行公式
	```
	$x_{min}+x_{max}$
	\begin{math} 
	x_{min}+x_{max} 
	\end{math}
	```
	* 换行公式
	```
	\begin{equation} 
	x_{min}+x_{max} 
	\end{equation}
	```
若不希望对公式自动编号，则在equation后加一个*。

#### 4 插入表格
```
\begin{table}[!h]
\centering
\begin{tabular}{ccccc} %c表示center居中，l表示left左对齐，r表示right右对齐
\toprule
Country& Life expectancy  &Population&Growth rate &Labour force  \\
\midrule
The U.S. & 77 &30.393& 1 &99  \\
Canada & 79 &3.077&1  &100 \\
China & 71 &133.42&0.8  &92 \\
Japan & 81 & 332.42&0.2  &100 \\
\bottomrule
\end{tabular}
\caption{Index data(Only a small part)}
\end{table}
```
## 三、OJ（Online Judge）的介绍及可能出现的问题

## 四、电脑硬件知识的普及及选购建议

### １　笔记本选购心得

首先讲一讲买电脑要看哪些指标。

我们总是现有一些难以满足的需求：玩游戏，搞图形，多任务同时运行，等等。也可能卖笔记本是为了轻便易于携带。那么这些外在指标是如何从硬件指标里体现出来的呢？

关于处理器，现在比较流行i5,i7。它们的性能体现在开多个程序同时运行会不会卡。我们打开任务管理器的时候就可以看到各种任务占用的内存。越多内存占用大的程序可以并行，这个电脑越不容易卡。然而，这个容不容易卡不仅仅由处理器决定。实际上这也包含了访存过程，在CPU功能不断增强，I/O设备不断增多时，主存的存取速度已经成为计算机的瓶颈。当然，CPU并不是完全访问主存的阿，也有CPU访问Cache的情况，而在这种情况下Cache命中率便很重要。既然这个问题如此复杂，那我们选购该怎么判断呢？开好多个程序看卡不卡还是最简单的了。当然，i３及以下的还是不要考虑作为上学使用的了。

之后，说一下显卡选购。目前市场上比较流行３种显卡：英伟达（NVIDA）,AMD,Intel.有一种说法是AMD拥有极致色彩，NVIDA做到了曲线细分，Intel动态模糊......不管怎么说，如果想做图形学做渲染英伟达还是不错的。

### 2  整笔记本推荐

> "没钱就上船，船翻了就修或者买新的。一个外星人可以买两个船。"
							——神舟论坛言论

确实神舟笔记本可以以较少的钱换来更好的硬件体验，没有钱可以试一试。
有钱的话戴尔外星人比较耐用，五年前买的现在还能跑Steam上的主流游戏。但是外星人散热不是很好。雷蛇灵刃散热更优于外星人，但是价钱也更高。我自己不太玩大游戏，从小学起一直用ThinkPad,比较基本的体验就是键盘很舒服（内置机械键盘），以及可以脱离鼠标（小红点＋快捷键）。




## 五、如何问问题？


## 六、优秀课外书籍推荐

* PPT制作相关——标题含图表术的都可以看看
* Latex论文写作入门——正确写作美国大学生数学竞赛论文
* 高等数学——前期可以做吉米多维奇 中后期考研真题
* 线性代数——线性代数应该这样学（比较难懂，但是思路和我们的教材不一样 答案在网上可以找到
* 英语学习——为了英文参考文献的阅读和英语论文的书写，我们需要有好的英语水平。由于数模比赛内容宽泛，可以在学英语的同时了解跨学科知识，比如政治经济新闻。推荐the Econmoist，Monocle,etc.


## 七、常见其它问题FAQ
