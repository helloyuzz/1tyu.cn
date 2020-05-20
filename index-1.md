---
title: "千里之行，始于足下，不积硅步，无以致千里!"
keywords: sample homepage
tags: [getting_started]
sidebar: mydoc_sidebar
permalink: index.html
summary: These brief instructions will help you get started quickly with the theme. The other topics in this help provide additional information and detail about working with other aspects of this theme and Jekyll.
---

{% include note.html content="If you're cloning this theme, you're probably writing documentation of some kind. I have a blog on technical writing here called <a alt='technical writing blog' href='http://idratherbewriting.com'>I'd Rather Be Writing</a>. If you'd like to stay updated with the latest trends, best practices, and other methods for writing documentation, consider <a href='https://tinyletter.com/tomjoht'>subscribing</a>. I also have a site on <a href='http://idratherbewriting.com/learnapidoc'>writing API documentation</a>." %}

## Build the Theme
# 排列 $ f(x) = P_n^m $ 与 组合 $ f(x)=C_n^m $ 

-----
__1.排列(Permutation)__ : __英__ [ˌpɜːmjuˈteɪʃn] ，排列; 置换; 数字排列的意思;

从n个被选数里面选择m个数 (n >= m)，假设选出的m个数和__次序有关__，公式如下：  

 !18 $ f(x) = P_n^m = \frac{n!}{(n-m)!} = \frac{1×2×3×...×(n-1)×n}{(n-m)!} $  ! 
  
<br>  
__阶乘__：法国数学家：!18__基斯顿.卡曼__! 在1808年发明  ，在数字尾部加感叹号！表示，如：  

n的阶乘 = n! = 1x2x3x ... x (n-1) x n，举例：

- 5的阶乘 = 5! = 1 x 2 x 3 x 4 x 5
- 16的阶乘 = 16！= 1 x  2 x 3 x ... x 14 x 15 x 16
  
<br>
(1-1) __题目1-1__：从5个士兵里面选出3个士兵，站成不同的队列，有多少种__不同__的选法？
__解__：分析题目中，问选出的士兵站成不同的队列，有多少种 "__不同的选法__" ，也就是选士兵的次序不同就会站成不同的队列，__跟次序有关__，所以采用[__排列__]的计算方法。

题目中，共有5个士兵，所以被选数n=5，选出的士兵m=3

公式：!18  $ f(x) = P_n^m  = \frac{n!}{(n-m)!} $ ! ，则：
!18  $ f(x) = P_5^3 = \frac{5!}{(5-3)!} = \frac{1×2×3×4×5}{2!} = \frac{1×2×3×4×5}{1×2} = 3×4×5 = 60(种) $ !

__答__：有60种选法。
 
<br>
(1-2) __题目1-2__: 现有8名运动员，将金银铜铁4块奖牌按金牌、银牌、铜牌、铁牌的次序颁给其中4名运动员，问一共有多少种颁奖方法？
解：分析题目中，按金牌、银牌、铜牌、铁牌的__次序__颁给3名运动员，__跟次序有关__，所以采用[__排列__]的计算方法。
题目中，共有8名运动员，所以被选数 n = 6，选出的运动员数量 m =3
公式：!18  $ f(x) = P_n^m = \frac{n!}{(n-m)!} $ ! ，则：
!18 $ f(x) = P_8^4 = \frac{8!}{(8-4)!} = \frac{1×2×3×4×5×6×7×8}{1×2×3×4} =5×6×7×8 = 1680(种) $ !

__答__: 有1680种颁奖方法。
<br>
__2.组合(Combination)__ ：__英__[ˌkɒmbɪˈneɪʃn]   结合体; 联合体; 混合; 字码组合的意思;
从n个被选数里面选择m个数 (n >= m)，假设选出的m个数和__次序无关__，公式如下：
 !18 $ f(x) = C_n^m = \frac{P_n^m}{m!} = \frac{\frac{n!}{(n-m)!}}{m!} =>(或者)=  \frac{n!}{(n-m)!} ×\frac{1}{m!} = \frac{n!}{(n-m)!×m!} $  ! ，也就是：<br><br>① 先计算排列，用 $ P_n^m $  公式计算第一步的值<br>② 然后再用第一步计算得出的值   !18÷! m!
<br>
(2-1) __题目2-1__：从5种水果里面，选出3种水果送给朋友，有多少种选法？
__解__:分析题目中，只要求选出3中水果送给朋友，不管先选哪种水果，只要数量=3就表示选择正确，也就是和__次序无关__，所以使用[__组合__]的计算方法。

题目中，有5中水果，所以被选数 n =5，选出的水果 m =3

组合公式一： !18 $ f(x) = C_n^m = \frac{P_n^m}{m!}  $  !，由于公式比较复杂，所以：
<br>
① 先计算排列，公式： !18  $ f(x) = P_n^m = \frac{n!}{(n-m)!} $ ! ，则：
!18 $ f(x) = P_5^3 = \frac{5!}{(5-3)!} = \frac{1×2×3×4×5}{2!} = \frac{1×2×3×4×5}{1×2} = 3×4×5 = 60(种)  $ !
 <br>
② 然后用上面计算得出的结果 60/m!，计算如下： 
!18 $ f(x) = \frac{P_n^m}{m!}  = \frac{60}{m!}  = \frac{60}{3!}= \frac{60}{1×2×3} = 10(种)  $ !
<br>
__答__:从5中水果里面，选出3中水果送给朋友，有10中选法。
<br>

(2-2) __题目2-2__: 从8名运动员里面选出4人,每人发一瓶可乐,一共有多少种选法?
__解__: 每人发一瓶可乐,很明显和__次序无关__,所以适合__组合__计算方式.

组合公式二： !18 $ f(x)=C_n^m =  \frac{n!}{(n-m)!×m!} $ ! ,则:

!18 $ f(x) = C_8^4 = \frac{8!}{(8-4)!×4!} = \frac{1×2×3×4×5×6 ×7×8}{(8-4)! ×(1×2×3×4)} = \frac{1×2×3×4×5×6 ×7×8}{ (1×2×3×4)×(1×2×3×4)} = \frac{43020}{ 24×24}=\frac{43020}{576} =70(种) $ !
<br>
__答__: 从8名运动员里面选出4人,每人发一瓶可乐,一共有70种选法。

{% include links.html %}
