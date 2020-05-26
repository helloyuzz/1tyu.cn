---
title: "千里之行，始于足下，不积硅步，无以致千里!"
# keywords: Jekyll Exercise-book
# tags: [getting_started]
sidebar: mydoc_index_navmenu
permalink: index.html
summary: Mathematical method penetration and dominate all branches of natural science theory. It becomes more and more become a symbol of the primary measure of scientific achievements..
---

{% include note.html content="本文中，主要讲解排列与组合的计算方法，同时参考部分示例进行说明，本文章内容，基于<a href='https://jekyllrb.com/' target='_blank'>Jekyll</a>和<a href='https://gems.ruby-china.com/' target='_blank'>Ruby gems</a>构建，同时采用的<a href='https://github.com/mathjax/MathJax' target='_blank'>MathJax</a>显示文章中的数学公式。." %}

## 排列 $ f(x) = P_n^m $ 与 组合 $ f(x)=C_n^m $ 

### __1.排列(Permutation)__ :  
 Permutation， __英__ [ˌpɜːmjuˈteɪʃn] ，排列; 置换; 数字排列的意思;

从n个被选数里面，选择m个数 (m <= n)，对选出的m个数按照一定的顺序进行排列，叫做从n个元素里面取出m个元素的一个排列，排列的结果和取出元素的 __次序有关__，公式如下：  

 $ f(x) = P_n^m = \frac{n!}{(n-m)!} = \frac{1×2×3×...×(n-1)×n}{(n-m)!} $  

<br>  


__阶乘！__：法国数学家：__基斯顿.卡曼__ 在1808年发明  ，在数字尾部加感叹号！表示，一个数的阶乘 = 从自然数1开始递加相乘，直到该自然数本身，如：n的阶乘为：  

 n! = 1 x 2 x 3 x ... x (n-1) x n，举例：

- 5的阶乘， 5! = 1 x 2 x 3 x 4 x 5
- 16的阶乘， 16！= 1 x  2 x 3 x ... x 14 x 15 x 16
  
<br>
####  (1-1) __题目1-1__：从5个士兵里面选出3个士兵，分别站A、B、C三个岗位，有多少种不同的选择方法？
__解__：
分析题目中，问选出3个士兵，分别站A、B、C三个岗位，有多少种选择方法？也就是，选出的士兵次序不同，站的岗位就不同；说明跟选择的次序 __有关__，所以本题应该采用 __[排列]__ 的计算方法。

题目中，共有5个士兵，所以被选数n=5，选出的士兵数量m=3

排列公式：  $ f(x) = P_n^m  = \frac{n!}{(n-m)!} $  ，则：

  $ f(x) = P_5^3 = \frac{5!}{(5-3)!} = \frac{1×2×3×4×5}{2!} = \frac{1×2×3×4×5}{1×2} = 3×4×5 = 60(种) $  

__答__：有60种选择方法。

#### __图例分析__：

|士兵数量：|
| :--- |
|  `1`  -  `2`  -  `3`  -  `4`  -  `5` |  

|岗位|A岗|B岗|C岗| 
| :---: | :---: | :---: | :---: | :---: |
|__可选__:|5|4|3|


__第一步__：选择A岗，可以从5个士兵中任选一个，所以：有5个士兵可选；  
__第二步__：选择B岗，由于第一步已经选择了一个士兵，所以：还有4个士兵可选；  
__第三步__：选择C岗，前面选择了两个士兵，所以：还有3个士兵可选；  

那么，很明显，一共有： 5 X 4 X 3 种选法。
<br>

__以此类推,也可倒推出公式__ ，$ f(x) = \frac{n!}{(n-m)!} $ ，   步骤如下：

假设有5个岗位，那么按照上述方法，让每个士兵站一个岗位，直到每个岗位都站满，那么就有：5 X 4 X 3 X 2 X 1 种方法，也就是；

|岗位|A岗|B岗|C岗|`X`|`X`|  
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |  
|__可选__:|5|4|3|`2`|`1`|

但是，前面题目中，只需要ABC三个岗位，那么怎么减去多的部分呢？很简单：

只需要从`总的数量中`除去`不需要包括在内`的岗位数量即可，也就是从 5 × 4 × 3 × 2 × 1 除去：2 × 1，换算成公式：

  $ f(x) = \frac{5 × 4 × 3 × 2 × 1}{2 × 1} =\frac{5!}{(5-3)!}  = \frac{n!}{(n-m)!} $  ，即倒推出，排列公式： $ f(x) =P_n^m = \frac{n!}{(n-m)!} $ 

<br>
####  (1-2) __题目1-2__: 现有A、B、C、D、E、F、G、H，8名运动员，将金银铜铁4块奖牌按金牌、银牌、铜牌、铁牌的次序颁给其中4名运动员，问一共有多少种颁奖方法？
解：分析题目中，选出4名运动员，按金牌、银牌、铜牌、铁牌的 __次序__ 颁奖，那么就意味着：选出运动员次序的不同，颁奖结果就会不同，说明此题 __跟次序有关__，所以应该采用 __[排列]__ 的计算方法。

题目中，共有8名运动员，所以被选数 n = 8，选出的运动员数量 m =4

采用公式：  $ f(x) = P_n^m = \frac{n!}{(n-m)!} $  ，则：

 $ f(x) = P_8^4 = \frac{8!}{(8-4)!} = \frac{1×2×3×4×5×6×7×8}{1×2×3×4} =5×6×7×8 = 1680(种) $ 

__答__: 一共有1680种颁奖方法。
<br>
###  __2.组合(Combination)__ ：  

Combination， __英__[ˌkɒmbɪˈneɪʃn]   结合体; 联合体; 混合; 字码组合的意思;

从n个被选数里面，选择m个数 (m <= n)并成一组，叫做从n个元素里面取出m个元素的一个 __组合__，且组合跟元素的 __次序无关__，组合公式如下：

  $ f(x) = C_n^m = \frac{P_n^m}{m!} = \frac{\frac{n!}{(n-m)!}}{m!} =>(或者)=  \frac{n!}{(n-m)!} ×\frac{1}{m!} = \frac{n!}{(n-m)!×m!} $  ! ，也就是：<br><br>① 先用 $ P_n^m $  公式计算排列的结果<br>② 然后再用 $ P_n^m $  的结果 除以 m!
<br>
####  (2-1) __题目2-1__：水果店里有A苹果、B葡萄、C西瓜、D榴莲4种水果，现要购买2种水果送给朋友，有多少种购买方法？
__解__:分析题目中，现要购买2种水果送给朋友，也就是意味着，2种水果不管先选其中哪一种，选出的水果都是相同的，也就说明和 __次序无关__，所以使用 __[组合]__ 的计算方法。

题目中，有4中水果，所以被选数 n =4，选出的水果 m =2

__组合公式一__（第一种解法)：

  $ f(x) = C_n^m = \frac{P_n^m}{m!}  $  ，也就是：


- [x] 可以先用排列公式，计算出 __排列__   $ p_n^m $ 的结果；
- [ ] 然后从 __排列__   $ p_n^m $ 的结果里面，减去 __不参与排序__ 的数量m!；  
<br> 


分两步计算：

 __第①步__：先计算排列 $ P_n^m $ 

公式：   $ f(x) = P_n^m = \frac{n!}{(n-m)!} $ ! ，则：

 $ f(x) = P_4^2 = \frac{4!}{(4-2)!} = \frac{1×2×3×4}{2!} = \frac{1×2×3×4}{1×2} = 3×4 = 12(种)  $ 
 
 __第②步__：然后用上面计算得出的结果，也就是： $ \frac{12}{m!} $ ，计算如下： 

 $ f(x) = \frac{P_n^m}{m!}  = \frac{12}{m!}  = \frac{12}{2!} = \frac{12}{1×2} = 6(种)  $  

__答__：从4中水果里面，选出2种水果送给朋友，有6种选择方法。
<br>
#### `详细分析`：  

|`已知：水果店里有4种水果：`|
| :--- |
|  `苹果`  -  `葡萄`  -  `西瓜`  -  `榴莲`    |  

<br>

__第①步__：先计算排列的值 $ f(x) = P_n^m $  

| `备选水果` |`选第一种`|`选第二种`|`-`|`-`|  
| :---: | :---: | :---: |  :---: | :---: |
| _`水果种类`:_ | 4 | 3 | - | - |  



 $ f(x) = P_n^m = P_4^2 = {\frac{4!}{(4-2)！}} = {\frac{1×2×3×4}{2!}} $ = 4 × 3 = 12(种)

组合几种不同的情况，结果如下：  
<table>
  <tr>
    <td colspan="2">一选A</td>
    <td colspan="2">一选B</td>
    <td colspan="2">一选C</td>
    <td colspan="2">一选D</td>
  </tr>
  <tr>
    <td>①</td>
    <td>②</td>
    <td>①</td>
    <td>②</td>
    <td>①</td>
    <td>②</td>
    <td>①</td>
    <td>②</td>
  </tr>
  <tr>
    <td style="background:red;color:#ffffff;">A</td>
    <td style="background:red;color:#ffffff;">B</td>
    <td style="background:red;color:#ffffff;">B</td>
    <td style="background:red;color:#ffffff;">A</td>
    <td colspan="4"></td>
  </tr>
  <tr>
    <td style="background:green;color:#ffffff;">A</td>
    <td style="background:green;color:#ffffff;">C</td>
    <td colspan="2"></td>
    <td style="background:green;color:#ffffff;">C</td>
    <td style="background:green;color:#ffffff;">A</td>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td style="background:blue;color:#ffffff;">A</td>
    <td style="background:blue;color:#ffffff;">D</td>
    <td colspan="4"></td>
    <td style="background:blue;color:#ffffff;">D</td>
    <td style="background:blue;color:#ffffff;">A</td>    
  </tr>
  <tr>
  <td colspan="2"></td>
    <td style="background:#ff00ff;color:#ffffff;">B</td>
    <td style="background:#ff00ff;color:#ffffff;">C</td>
    <td style="background:#ff00ff;color:#ffffff;">C</td>
    <td style="background:#ff00ff;color:#ffffff;">B</td>
    <td colspan="2"></td>
  </tr>
  <tr>
    <td colspan="2"></td>
    <td style="background:blue;color:#ffffff;">B</td>
    <td style="background:blue;color:#ffffff;">D</td>
    <td colspan="2"></td>
    <td style="background:blue;color:#ffffff;">D</td>
    <td style="background:blue;color:#ffffff;">B</td>
  </tr>
  <tr>
    <td colspan="4"></td>
    <td style="background:green;color:#ffffff;">C</td>
    <td style="background:green;color:#ffffff;">D</td>
    <td style="background:green;color:#ffffff;">D</td>
    <td style="background:green;color:#ffffff;">C</td>
  </tr>  
</table>
<br>

|1|2|3|4|5|6|7|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|`A`|`B`|`C`|||||
|A|B|D||`B`|`A`|`C`|
|A|B|E||`B`|`C`|`A`|
||||||
|`A`|`C`|`B`||`C`|`A`|`B`|
|A|C|D||`C`|`B`|`A`|
||||||||

从上面表格中可以看出：
- [x] 任选两种水果，必然会出现AB<-->BA，AC<-->CA，AD<-->DA重复排序的情况，也就是被重复排序了 2 × 1 遍；
- [ ] 如果选择的是3种，那么选择的三种水果A、B、C会被重复排列3 × 2 × 1 = 6遍

__上题中：每种选择被重复排列了 2 × 1 次__ ，但实际 __只需要排列一次__ ，所以应该从总的数量中除以重复排列的次数，也就是：
- [x] 选择的数量 m = 2，也就是除以2!

<br>

__所以，第②步__  计算  $ f(x) = \frac{第①步的值}{重复计算的次数} =  \frac{第①步的值}{m!} $  ，也就是排除重复计数的 __次数__，重复了几次，就除以几次，以保证只排序一次。

通过前面的计算，得出排列的 __总数量__  = 12(种)，参见[ `__第①步__ 计算得出` ]，但由于有 m 种水果重复排序，所以：__`需要从 '总数量' 里面除去 '重复排序' 的次数`__，`重复次数 = m! = 2! = 2 × 1` 种，即：

`数量` $  = \frac{12}{m!} = \frac{12}{2!} = \frac{12}{2 × 1} = 6(种) $ ，所以：
<br>

__答__：从4中水果里面，选出2种水果送给朋友，有6种选择方法。

<br>
####  (2-2) __题目2-2__: 从A、B、C、D、E、F、G、H，8名运动员里面选出4名运动员，每人发一瓶可乐，一共有多少种选择方法?
__解__: 每人发一瓶可乐，因为不管先选出哪位运动员，发的都是相同的可乐，所以结果都是一样的，很明显此题和 __选择次序无关__，所以适合 __[组合]__ 的计算方式.

__组合公式二__（第二种解法）：

 - $ f(x) = C_n^m = \frac{P_n^m}{m!}  $  ，公式化简： $ f(x) = \frac{P_n^m}{m!} = \frac{\frac{n!}{(n-m)!}}{m!} = \frac{n!}{(n-m)!} × \frac{1}{m!}=  \frac{n!}{(n-m)!×m!} $  ，得：

 - $ f(x) = C_n^m = \frac{n!}{(n-m)! × m!} $ ，带入数据计算，得：

 - $ f(x) = C_8^4 = \frac{8!}{(8-4)!×4!} = \frac{1×2×3×4×5×6 ×7×8}{(8-4)! ×(1×2×3×4)} = \frac{1×2×3×4×5×6 ×7×8}{ (1×2×3×4)×(1×2×3×4)} = \frac{43020}{ 24×24}=\frac{43020}{576} =70(种) $ 

<br>

__答__: 从8名运动员里面选出4名运动员，每人发一瓶可乐，一共有70种选择方法。

<br>
## 总结
 - [x] `阶乘!`：首先需掌握 __阶乘！__ 的概念和计算方法；n! = 1 × 2 × 3 × ... × (n-1) × n.
 - [x] `如何选择`：
   - 针对该用 __排列__ 还是 __组合__ ，主要是看实际应用中，结果是否跟顺序有关？，有关系，用排列计算方法；无关，用组合计算方法；
 - [X] `联系`：
    - 都是从 n 个元素里面取出 m 个元素（m <= n）；
 - [x] `区别`：
    -  前者是，取出的元素按照顺序 __“排成一列”__，也就是和 __顺序有关__；
    -  后者是，取出的元素 __“并成一组”__，和 __顺序无关__。

## Author: helloyǎn & hellóyuzz
{% include links.html %}
