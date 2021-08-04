---
title:       "LaTexにおける場合分けの環境"
subtitle:    ""
description: "displaystyleで表示"
date:        2021-08-04
author:      "Kazuma Kano"
image:       true
tags:        [latex]
categories:  []
published:   true
---

LaTexで場合分けを記述するための環境についてまとめます。

# cases
`cases`は場合分けを記述するための環境の1つです。
使用するには`amsmath`パッケージをインクルードする必要があります。
デフォルトでは`\textstyle`になっているため、分数などは窮屈に表示されてしまいます。
```
$$
f(x)=
\begin{cases}
    0 & (x < 0) \\
    \frac{x}{2} & (x \ge 0)
\end{cases}
$$
```
![cases](../../img/post-20210804-01.png)

`\displaystyle`を明示的に指定することもできます。
```
$$
f(x)=
\begin{cases}
    0 & (x < 0) \\
    \displaystyle \frac{x}{2} & (x \ge 0)
\end{cases}
$$
```
![cases](../../img/post-20210804-02.png)

# dcases
一方、`dcases`環境ではデフォルトで`\displaystyle`になっています。
わざわざ`cases`環境で`\displaystyle`を指定するよりも、こちらの環境を使った方が楽です。
使用するには`mathtools`パッケージをインクルードする必要があります。

# cases*
`cases`環境では左側の値と右側の条件はどちらも`\textstyle`でしたが、条件のみデフォルトで`\text`になった`cases*`という環境もあります。
条件に数式ではなく文章を多く記述する場合に有用です。

同様に、値は`\displaystyle`で条件が`\text`である`dcases*`という環境もあります。
これらを使用するのに必要となるパッケージはアスタリスク無し環境と同じです。
