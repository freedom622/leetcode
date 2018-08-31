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
*1, it also uses doubly linkedlist and hashmap internally. 
*2, The paramter "accessOrder" for constructor is importnat, when implementating LRU, it should be true. (True is access-order, False is insertion-order)
**********************************************
