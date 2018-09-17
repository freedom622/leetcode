Current Problem 5

From Sep9 to Dec 9, by type. 100 topics and Google. 

# Leetcode
Leetcode questions summary Category

**1, Sum problem**
**********************************************

```
1.1 (1) Two Sum
```
```
1.2 (15) 3 Sum
```
```
1.3 (18) 4 Sum
```
```
1.4 (454) 4 Sum II
```
```
1.5 (167) Two Sum II - Input array is sorted
```
```
1.6 (170) Two Sum III - Data structure design
```
```
1.7 (653) Two Sum IV - Input is a BST
```
```
1.8 (560) Subarray Sum Equals K
```

## Summary

For Sum Issue, 
* generally two approaches: 
    one is two pointers skill
    the other is using Map
* for two pointers skill, it only works when the array is sorted so that you know which direction the pointer will move to. 
* for map skill, the array can be not ordered, you can check if (target-current) exists or not in the map. 

**********************************************


**2, LinkedList Problem**
**********************************************

```
2.1 (2) Add Two Numbers
```
```
2.x (206) Reverse Linked List
```
## Summary

For LinkedList problem, 
* using the dummy head you do not need to check if current node is the first node or not, making the code clean


**********************************************


**3, Math Problem**
**********************************************

```
3.1 (2) Add Two Numbers
```
```
3.2 (43) Multiply Strings
```
```
3.3 (67) Add Binary
```
```
3.4 (415) Add Strings
```
```
3.5 (445) Add Two Numbers II
```
```
3.6 (9) Palindrome Number
```
```
3.7 (9) Reverse Integer
```
## Summary

For Math problem, 
* use integer array to save the number for each bit
* add from end to the front, skip the front zero value 
* do not forget the carry (bring over the carry)

**********************************************


**4, Bit Manipulation Problem**
**********************************************

```
4.1 (371) Sum of Two Integers
```

## Summary

For Bit Manipulation problem, 
* 

**********************************************

**5, String Problem**
**********************************************

5.1 Slide Window Skill

```
5.1.1 (3) Longest Substring Without Repeating Characters
```
```
5.1.2 (76) Minimum Window Substring
```
```
5.1.3 (209) Minimum Size Subarray Sum
```
```
5.1.4 (438) Find All Anagrams in a String
```

5.2 Palindromic Problem
```
5.2.1 (5) Longest Palindromic Substring
```


## Summary

For String problem, 
(1) Slide window skill summary
* this skill only apply to continuous problem (substring or subarray)
* it can greatly improve time complexity

**********************************************

**6, Design Problem**
**********************************************

```
6.1 (146) LRU Cache
```
```
6.2 (155) Min Stack
```
```
6.3 (173) Binary Search Tree Iterator
```
## Summary

For Design Problem,

* the benefit of doubly linkedList
(1) O(1) to remove, modify and add a node if you get hold of a node (single linkedlist can not since it does not know the previous node)
(2) How to combine the benefit of two data structures ? for example, fast search using hashmap and remove the last element in access order using doubly linkedlist. The value can be a doubly linkedlist node for hashmap. 

LinkedHashMap summary
* 1, it also uses doubly linkedlist and hashmap internally. 
* 2, The paramter "accessOrder" for constructor is importnat, when implementating LRU, it should be true. (True is access-order, False is insertion-order)
**********************************************

**********************************************

**7, Two Pointers Skill**
**********************************************

```
7.1 (11) Container With Most Water
```
```
7.2 (42) Trapping Rain Water
```
```
7.3 (253) Meeting Room 
```
## Summary

For Two pointer Skill,

* 1, using stack, you can calculate the dent. 
* 2, how to find the dent and check the water using two pointers method ? 
**********************************************

**8, Stack problem**
**********************************************

```
8.1 (20) Valid Parentheses
```
```
8.2 
```

## Summary

For Stack Skill,
**********************************************

**9, Dynamic programming**
**********************************************

```
9.1 (20) Valid Parentheses
```
```
9.2 (5) Longest Palindromic Substring
```

## Summary

For DP Skill,
* How to understadnd Overlapping subproblem and optimal substructure ?
* Overlapping subproblem: 也就是说一个问题可以分解成规模较小的类似的子问题。（当做一颗树，发现子树中有很多重复的时候，说明是重叠子问题）
* Optimal substructure: 每个阶段的最优状态可以从之前某个阶段的某个或某些状态直接得到而不管之前这个状态是如何得到的。 (比如：自下而上的方式中，当前状态可由之前某些状态直接运算得到) 这个其实就是找递推公式的过程，如果能找到递推公式，并且当前的结果要依赖之前的结果，那么就满足这个特性。

状态转移方程中，等式右边不会用到下标大于左边i或者k的值，这是"无后效性"的通俗上的数学定义，符合这种定义的状态定义，我们可以说它具有“最优子结构”的性质，在动态规划中我们要做的，就是找到这种“最优子结构”。

For Example: 
1.最优子结构            
从图中可以看到如果要求解斐波那契的第i项,必须要求出斐波那契的i-1项和斐波那契的第i-2项;换句话说就是斐波那契的第i项的解包括斐波那契的第i-1项和斐波那契的i-2项的解；这个性质就叫做最优子结构也就是一个问题的一个最优解中包含了子问题的最优解

2.重叠子问题           
可以看出某些状态(或者说是子问题)被多次调用，这个性质就叫做重叠子问题。

3.为什么要自底而上的求解            
自底而上的求解可以避免重复计算重叠的子问题

总之，动态规划其实就是一种优化技术，这中技术适用于在有重复计算的场景中，缓存计算结果，当下次需要结果的时候直接取出结果而不是再次计算。（所以，一般只有在重叠子问题，并最优子结构的时候，才会适用这种优化，否则并不能得到太多时间复杂度的提升）

对于二维动态规划（比如挖金问题），通过列出递归式，可以说是满足最优子结构，并能看出有重叠子问题。（二维不能通过画树，而要通过画表格才能体会是否有重叠字问题），对于重叠字问题，因为递归式是DP(i,j) = MAX(DP(i-1,j-3)+200, DP(i-1,j)), DP(i-1,j) and DP(i-1,j-3)很有可能被好几个下一行的计算重复的使用，所以一定要存储起来，这样可以有效减少计算，也就是动态规划的核心之一，memorization。 

https://aaronice.gitbooks.io/lintcode/content/dynamic_programming/maximum_product_subarray.html
https://blog.csdn.net/column/details/24281.html

**********************************************

**10, Sort Problem**
**********************************************

```
10.1 (252) Meeting Room I
```
```
10.2 (253) Meeting Room II
```
## Summary

**********************************************

**11, Union find Problem**
**********************************************

```
11.1 (547) Friend Circles
```

## Summary

**********************************************
