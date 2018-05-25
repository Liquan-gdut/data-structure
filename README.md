各种数据结构的物理本质、逻辑与存储结构、模型
树和二叉树的遍历、最优二叉树、图的最小生成树
查找算法
排序算法
一、数据结构
线性表、栈和队列、串：物理本质，逻辑、存储结构，对应模型，应用案例
树和二叉树、图：逻辑与存储结构，遍历方法，最优二叉树算法、最小生成树算法
1、线性表
（1）本质定义：一系列逻辑上相邻的有限序列。
（2）逻辑结构：线性结构，除第一个外，所有元素只有一个前驱，除最后一个外，所有元素只有一个后继
（3）存储结构：
     ①顺序存储：在物理内存上也是一序列相邻的空间。
     ②链式存储：在物理内存中不一定相邻。单链表，每个结点包含数据和一个指向后继的指针；双链表，每个结点包含                         数据和两个指针，一个指向前驱一个指向后继；
2、栈和队列
（1）本质定义：
       栈：被限制的线性表，只能“后进先出”。经典模型：饼干桶模型
      队列：被限制的线性表，只能“先进先出”，从头部输出，从尾部输入。经典模型：排队打饭模型
3、串
（1）本质定义：就是字符串了。
（2）存储结构
       ①顺序存储
       ②堆分配存储：可根据“串长”动态分配数组长度。
       ③链式存储：数据域+指针域
（3）子串匹配算法
       ①普通算法：循环匹配→回退→匹配→循环次数=原串-子串
       ②模式匹配(KMP)算法：
          适合“子串”与“父串”存在大量相似元素的情况（略）
4、树和二叉树
（1）本质定义：一种非线性结构，递归的概念：每个节点可以分成若干不相交节点，每个节点（除根节点外）只有一个                        父节点。
（2）经典模型：家族谱，层次结构。
（3）二叉树的存储结构：
        ①顺序：每个结点打上完全二叉树的标号，存到数组对应位置中；
        ②(常用)链式：左孩子指针+数据+右孩子指针
（4）树的存储结构：①父亲表示法：数据+父节点指针；②孩子表示法：数据+每个孩子
（5）二叉树的遍历
基本原则：先左后右，递归
①先根遍历：根左右
②中根遍历：左根右
③后根遍历：左右根
（6）最优二叉树（赫夫曼树）
     ①经典模型：成绩评定
     ②本质定义：每个叶子结点都“带权”（权就是代价），到每个节点的带权总和最小的二叉树，称为最优二叉树
     ③算法：
将所有带权节点放入同一个集合当中
集合中取出(并删除)两棵根节点最小的二叉树，作为左右子树，根节点和为新的根节点，
生成的二叉树再加入到集合当中
重复上面两步骤
（7）赫夫曼编码：遵循“左‘0’，右‘1’”原则
5、图
（1）本质定义：多对多的非线性结构
（2）图的遍历
     ①深度优先
        执行机制：类似于“先根遍历”，以某节点为出发点→先根遍历→遇到重复就回退→所有节点访问完则截止
     ②广度优先
        执行机制：按层次遍历，先上后下，亲兄弟同时访问，堂兄弟先左后右。
（3）最小生成树算法
    经典模型：城市交通网
    算法：
建集合U，并入一个起始节点
找出到集合U的最小代价边，并入新节点到U
重复步骤2
二、经典算法
    算法衡量指标：①存储效率，执行效率，即空间效率，时间效率
1、查找算法
（1）顺序查找：针对排好序的序列
    ①普通的全表遍历查找
    ②二分法查找
    ③插值查找：改进的二分法，自适应二分法
       算法过程：mid=[（目标值 - 序列最小值）/（序列最大值 - 序列最小值）] *序列长度
    ④斐波那契查找：黄金分割系数
    ⑤分块查找：块内无序，块间有序
（2）树查找
    ⑥二叉排序树
       算法过程：
二叉搜索树：左子树小于根节点，右子树大于根节点
二叉搜索树构造过程：现将序列排序，中点递归
插入过程：先序遍历进行比较
    ⑦平衡2-3排序树
        本质：二叉排序树的改进，有二叉树，也有三叉树。
    ⑧红黑树
       本质：2-3排序树的改进，能转化的全部转化为三叉树
    ⑨B/B+树（待完善）
（3）哈希查找：牺牲存储效率，换取查找效率
    ①将序列进行哈希存储，确定“定址”、“冲突”方案
    ②算法：目标值输入到哈希函数，与对应地址的值进行比较→若位置为空，则结果为空，相等则输出位置，不等则进                  行“冲突处理”(如线性探测)→若位置为空，则结果为空，相等则输出位置，不等则进行“再冲突处理”(如二次                   线性探测)→相等则输出，不等则输出结果。
2、排序算法
（1）非线性比较类
（2）线性非比较类
![image](https://github.com/Liquan-gdut/data-structure/blob/master/%E5%8D%81%E5%A4%A7%E6%8E%92%E5%BA%8F%E7%AE%97%E6%B3%95.png)
整体总结：
1、线性表、二叉树的逻辑与存储结构
2、二叉树的遍历算法
3、查找、排序算法（平时多练习，采用js、Python、C++等语言实现）
