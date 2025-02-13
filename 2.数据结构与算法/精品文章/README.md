|         递归         |           数组           |             链表             |                   树                   |               哈希               |         子序列/子串问题         |           滑动窗口           |          回溯          |          动态规划          |               贪心               |           DFS           |             BFS             |          剑指 offer           |
| :------------------: | :----------------------: | :--------------------------: | :------------------------------------: | :------------------------------: | :-----------------------------: | :--------------------------: | :--------------------: | :------------------------: | :------------------------------: | :---------------------: | :-------------------------: | :---------------------------: |
| [:corn:](#corn-递归) | [:tomato:](#tomato-数组) | [:eggplant:](#eggplant-链表) | [:evergreen_tree:](#evergreen_tree-树) | [:watermelon:](#watermelon-哈希) | [:pear:](#pear-子序列-子串问题) | [:banana:](#banana-滑动窗口) | [:melon:](#melon-回溯) | [:peach:](#peach-动态规划) | [:strawberry:](#strawberry-贪心) | [:grapes:](#grapes-DFS) | [:cherries:](#cherries-BFS) | [:family:](#family-剑指offer) |

# 撸题小技巧

1. [JS 刷题总结](https://www.cnblogs.com/wuguanglin/p/SummaryOfJSDoAlgorithmProblem.html)
2. 判断奇偶：

    ```
    // 判断奇偶
    evenNum & 1 === 0; // 偶数
    oddNum & 1 === 1; // 奇数
    ```

3. 位运算中，把一个整数减一，在和原整数作与运算，会把该正数最右边一位的 1 变成 0.

# :speaking_head: 好文章汇总

1. [labuladong 的刷题三件套](https://labuladong.gitee.io/algo/2/17/)

# :corn: 递归

## 可用递归解决的问题

只要满足以下三个条件，就可以尝试使用递归来解决问题（摘自[数据结构与算法之美专栏](https://time.geekbang.org/column/article/41440)）：

1. **一个问题的解可以分解为几个子问题的解**。

    子问题就是数据规模更小的问题。

2. **这个问题与分解之后的子问题，除了数据规模不同，求解思路完全一样**。

3) **存在递归终止条件**。

用递归方法最关键的问题在于**写出递推公式，找到终止条件**。

写递归代码的关键就是找到如何将大问题分解为小问题的规律，并且基于此写出递推公式，然后再推敲终止条件，最后将递推公式和终止条件翻译成代码。

## 递归中的重复计算问题

最常见的比如青蛙跳台阶问题，斐波那契数列，在使用递归方式去解决问题时，代码会写成：

```
f(n) = f(n-1) + f(n-2)
```

假设 n 为 4，那么需要计算`f(3)`和`f(2)`；n 为 5 时还是需要计算`f(3)`，这里就对`f(3)`进行了不必要的重复计算。

解决这个问题时候，针对跳台阶问题当然可以用几个临时变量来解决，同时，也存在一个通用的方法，可以用一个散列表将计算结果保存：

```javascript
function f(n) {
    if (n === 1) return 1;
    if (n === 2) return 2;

    if (map.has(n)) {
        return map.get(n);
    }

    let res = f(n - 1) + f(n - 2);
    map.set(n, res);
    return res;
}
```

# :peach: 动态规划

[背包九讲](背包九讲/背包九讲.pdf)

[动态规划解析-322 题题解](https://leetcode-cn.com/problems/coin-change/solution/dong-tai-gui-hua-tao-lu-xiang-jie-by-wei-lai-bu-ke/)
