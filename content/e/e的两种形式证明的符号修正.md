---
title: e的两种形式证明的符号修正
author: Rob Zhou
date: "2022-01-12"
categories:
  - 数学
tags:
  - e的小书
---

在原来的 e 的两种形式的等价性证明中，由于使用的符合很容易让人产生误解。原证明，比如下面的。

$$ \lim_{n\to\infty}{(1+\frac{1}{n})}^n=\lim_{n\to\infty} { \left[1+1+\frac{1}{2!}\frac{n(n-1)}{n^2}+\frac{1}{3!}\frac{n(n-1)(n-2)}{n^3}+...+\frac{1}{(n-1)!}\frac{n(n-1)...2}{n^{n-1}}+\frac{1}{n!}\frac{n(n-1)..1}{n^n} \right]}$$

提取出每项阶乘的倒数只有，其余的部分应该都为 1.

但是我们却发现。这项似乎不为 1。比较明显的例子，看最后一项。

$$\frac{n(n-1)..1}{n^n}$$

分子有 n 项，分母也有 n 项。考察前面的项。如第一项为`$\frac{n}{n}=1$`。而第二项`$\frac{n-1}{n}=(1-\frac{1}{n})$`,当`$n\to\infty$`时也为 1。于是我们凭借直觉会觉得后面的每一项都是 1.

但是最后一项却给我们当头一棒。最后一项为`$\frac{1}{n}=0$`。即便 n 写成`$n-(n-1)$`的巧妙形式：

$$\frac{n-(n-1)}{n}=1-\frac{n-1}{n}$$

如果你去考察在`$n\to\infty$`时，上式只能为 0。

难道我们的证明思路有问题？还是说我这两个式子并不相等？

首先，这个 e 的两个形式是肯定相等的。除非我们证明其不相等。

其次我们回顾我们的证明思路，并没有明显的问题。那问题出在哪里呢？

我们符号使用的混乱！

接下来，我要把符号修正后的证明写在下面：

$$\lim_{n\to\infty}{(1+\frac{1}{n})}^n $$

$$ = \lim_{n\to\infty}\sum_{i=0}^{n} C_n^i\frac{1}{n^i} $$

$$ = \lim_{n\to\infty}\sum_{i=0}^{n} \frac{n!}{i!(n-i)!}\frac{1}{n^i}$$

$$ = \lim_{n\to\infty}\sum_{i=0}^{n} \frac{1}{i!} \left[\frac{n!}{(n-i)!}\frac{1}{n^i} \right]$$

考虑中括号内的项,分子和分母都为i项

$$ \frac{n(n-1)...(n-i-1)}{n...n}=1(1-\frac{1}{n})...(1-\frac{i-1}{n}) $$

考虑其形式可以简化为

$$ \sum_{j=0}^{i}(1-\frac{j-1}{n}) $$

于是原式为：

$$ \lim_{n\to\infty}\sum_{i=0}^{n} \frac{1}{i!} \left[\sum_{j=0}^{i}(1-\frac{j-1}{n}) \right]$$

在内部对应n来说j是常量。于是可以得到
$$\lim_{n\to\infty}\left[\sum_{j=0}^{i}(1-\frac{j-1}{n}) \right]=1$$

于是原式化为

$$ \lim_{n\to\infty} \sum_{i=0}^{n} \frac{1}{i!} = \sum_{n=0}^{\infty}\frac{1}{n!}$$

