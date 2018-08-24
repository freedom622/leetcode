# Leetcode
Leetcode questions summary Category

1, Sum problem
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


2, LinkedList Problem
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


3, Math Problem
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

## Summary

For Math problem, 
* use integer array to save the number for each bit
* add from end to the front, skip the front zero value 
* do not forget the carry (bring over the carry)

**********************************************

