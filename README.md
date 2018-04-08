# 微信2048
## 效果图
![](https://github.com/windlany/2048/blob/master/img/index.png)
![](https://github.com/windlany/2048/blob/master/img/exp1.png)
![](https://github.com/windlany/2048/blob/master/img/exp2.png)
## 算法
该程序主要难度在用户滑动屏幕时值相同的cell合并 
将空格标为0（我代码中是用的""表示空格），假设棋盘如下：
- 0  2  0  2
- 0  0  0  0
- 0  0  0  2
- 0  0  0  0
### 步骤
- 通过touch相关的事件函数确定用户滑动方向
- 将棋盘的数字生成4*4的二维数组list
- 根据用户滑动方向生成四个小数组，比如用户将上面的棋盘向右滑动，则四个数组为：
> item[0] = [2, 0, 2, 0];
> item[1] = [0, 0, 0, 0];
>item[2] = [2, 0, 0, 0];   // 注意是2000而不是0002，因为是向右滑动要从右边开始
> item[3] = [0, 0, 0, 0];
- 接下来就是滑动时合并，拿item[0]举例，如果是2020，向右滑动我们应该成为0004
>- 将item[0]的所有0移到末尾变为2200，遍历item将相同的下标值相加，后面的数置为0
>- 2020 ---> 2200 ---> 4200 ----> 4000
- 如法炮制就可以实现滑动时合并 
