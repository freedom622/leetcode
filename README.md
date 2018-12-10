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

Doubly LinkedList problem, 
How to implement the doubly linkedlist ?
Initial implementation: 

class DoubleLinkedList {
        Node head;
        Node tail;

        DoubleLinkedList() {
            head = null;
            tail = null;
        }

        // add a new node
        public Node push(int it) {
            if (head == null) {
                head = new Node(it);
                tail = head;
            } else {
                Node nn = new Node(it);
                tail.next = nn;
                nn.pre = tail;
                // reset tail;
                tail = nn;
            }
            return tail;
        }

        public int pop() {
            int ret = tail.value;
            Node pre = tail.pre;
            if (pre != null) {
                pre.next = null;
            }
            tail.pre = null;
            tail = pre;
            if (tail == null) {
                head = null;
            }
            return ret;
        }

        public int top() {
            return tail.value;
        }

        // delete a node
        public void delete(Node node) {
            Node pre = node.pre;
            Node next = node.next;
            if (pre != null) {
                pre.next = node.next;
            } else {
                head = next;
            }
            if (next != null) {
                next.pre = node.pre;
            } else {
                tail = pre;
            }
        }

    }

Since head or tail may be null, I need to check if head or tail equals to null a lot, which is not good. 
Improved version: 

class DoubleLinkedList {
        Node head;
        Node tail;

        DoubleLinkedList() {
            head = new Node(0);
            tail = new Node(0);
            head.next = tail;
            tail.pre = head;
        }

        // add a new node
        public Node push(int it) {
            Node x = new Node(it);
            x.pre = tail.pre;
            x.next = tail;
            tail.pre = x;
            x.pre.next = x;
            return x;
        }

        public int pop() {
            return delete(tail.pre).value;
        }

        public int top() {
            return tail.pre.value;
        }

        // delete a node
        public Node delete(Node node) {
            Node pre = node.pre;
            Node next = node.next;
            pre.next = next;
            next.pre = pre;
            return node;
        }

    }
there is a dummy head and tail making the code concise and clear. 
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
```
6.4 (716) Max Stack
```
## Summary

For Design Problem,

* the benefit of doubly linkedList
(1) O(1) to remove, modify and add a node if you get hold of a node (single linkedlist can not since it does not know the previous node)
(2) How to combine the benefit of two data structures ? for example, fast search using hashmap and remove the last element in access order using doubly linkedlist. The value can be a doubly linkedlist node for hashmap. 

LinkedHashMap summary
* 1, it also uses doubly linkedlist and hashmap internally. 
* 2, The paramter "accessOrder" for constructor is important, when implementating LRU, it should be true. (True is access-order, False is insertion-order)
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
```
7.4 (243) Shortest Word Distance
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

A better article
https://sophiesongge.github.io/leetcode/2017/02/15/buy-sell-stock.html

重叠子问题表示子问题之间是重叠的(<-_<- 废话), 即子问题的解可能在下一阶段的求解中被用到。举个简单的栗子, 大家都知道著名的Fibonacci数列, 从第三位开始, 每一位都是前面两位的和。 比如, f(10) = f(9) + f(8), 也就是说, 当我们计算第10位的时候, 需要用到第9位和第8位的结果, 即我们需要重新计算f(9)和f(8), 这就是”重叠子问题”。 当然, 如果我们将f(9)和f(8)的结果缓存起来 – 比如用一个数组, 当我们 再次用到的时候只需要从缓存中将值读出即可, 而不需要进行重新计算。 — 简单的说, 就是一个以空间换时间的过程。

最优子结构, 如果我跟你说: 如果问题的最优解所包含的子问题的解也是最优的，我们就称该问题具有最优子结构性质。 — 你看了是不是很想去死啊…… 通俗一点说, 如果每个阶段的最优状态可以从前面的某个阶段的某个或某些状态直接得到, 则 可以说这个问题有最优子结构, — 再免费附赠一个概念叫“无后效应”, 不管之前那个状态是如何得到的, 则称其具有无后效应。 注意我这里用词是非常准确的, 某个阶段的某个状态或某些状态, 后面的题目中我们将会用到这一点。

但是在动态规划中, 我们并不能确定这一步的最优解是不是从上一步的最优解得来, 唯一能确定的是这一步的最优解肯定是从之前某一步的最优解得来的, 所以我们需要存储之前所有步的最优解。 如果还是觉得抽象可以去看看这道题。

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

classic implementation

// Union Find coding 
// https://www.jianshu.com/p/15cd02da4648
// http://bgmeow.xyz/2017/01/07/union-find/

public class UnionFind {

    private int[] id;
    private int[] size;
    private int count;

    public UnionFind(int N) {
        count = N;
        id = new int[N];
        for (int i = 0; i < N; i++) {
            id[i] = i;
        }
        size = new int[N];
        for (int i = 0; i < N; i++) {
            size[i] = 1;
        }

    }

    public int count() {
        return count;
    }

    public int find(int p) {
        int temp = p;
        while (p != id[p])
            p = id[p];
        id[temp] = id[p];
        return p;
    }

    public boolean connected(int q, int p) {
        return find(q) == find(p);
    }

    public void union(int p, int q) {
        int pRoot = find(p);
        int qRoot = find(q);

        if (pRoot == qRoot)
            return;

        if (size[pRoot] < size[qRoot]) {
            id[pRoot] = id[qRoot];
            size[qRoot] += size[pRoot];
        } else {
            id[qRoot] = id[pRoot];
            size[pRoot] += size[qRoot];
        }

        count--;
    }

}

**********************************************

**12, Topological Sort problem**
**********************************************

```
12.1 (207) Course Schedule
```

## Summary
The purpose of Topological sort is that
1, in a directed graph
2, for every directed edge UV from vertex U to vertex V, U comes before V in the ordering

what is the features of Topological sort?
Only DAG(directed acyclic graph) has at leat one topological ordering. So, if there is a cycle in a graph, so it does not have a topological ordering. By using this feature, we can check if there is a cycle in a directed graph. 

Where it is applied ?
This algorithm can be applied to those tasks which have dependencies for each other. For example, 
(1) Build systems
(2) Advanced-Packaging Tool (apt-get)
(3) Task Scheduling
(4) Pre-requisite problems

Why it can be applied to dependent tasks?
because only dependent tasks can be represented by directed graph. 

Another question when discussing with Q is, how to check a graph is all-connected?
For undirected graph, from any one point, do DFS or BFS, check if the number of points in the path sums to the number of vertex of the graph. 
For directed graph, 

From the implementation perspective, there are two methods:
1, BFS (Kahn's algorithm)
1.1 find those points which have the in degree value 0. 
1.2 enqueue them in a queue, and dequeue one from the queue (amount to removing the edge from this point to directed and connected points).
1.3 lessen one in-degree value and put the connected points to queue if the in-degreee becomes 0, return to 1.1. 
1.4 using an array to keep the order when dequeuing an element. 

2, DFS
2.1 Start from any point, and mark the node as temporily visited
2.2 Do DFS unitl no further node, mark it as visited, return to last node. 
2.3 Do DFS from this point again, until all points are vistied. 
If during DFS, visit a node which is temporily visited, then there is a loop, otherwise, put it in a stack. 



**********************************************

**13, Segment Tree**
**********************************************

```
13.1 (307) Range Sum Query - Mutable
```
## Summary

Implementation: 

class SegmentTree{
        
        int[] tree; // use array to save tree
        int n; // the number of elements in the array
        
        //init a segment tree (time complexity is: O(n))
        public SegmentTree(int[] nums){
            if(nums.length>0){
                n = nums.length;
                tree = new int[n*2];
                buildTree(nums);
            }
        }
        
        private void buildTree(int[] nums){
            for(int i=n,j=0;i<n*2;i++,j++){
                tree[i] =nums[j]; 
            }
            for(int i=n-1;i>0;i--){
                tree[i] = tree[i*2]+tree[i*2+1];
            }
        }
        
        //update a tree node, TC is O(logn)
        public void update(int pos, int val){
            int treePos = pos + n;
            tree[treePos] = val;
            while(treePos>0){
                int left = treePos;
                int right = treePos;
                if(treePos%2==0){
                    right = treePos+1;
                } else {
                    left = treePos-1;
                }
                tree[treePos/2] = tree[left]+tree[right];
                treePos /=2;
            }
        }
        
        //get the sum TC:O(logn)
        public int sumRange(int left, int right){
            left += n;
            right += n;
            int sum = 0;
            while(left<=right){
                if(left%2==1){
                    sum+=tree[left];
                    left++;
                }
                if(right%2==0){
                    sum+=tree[right];
                    right--;
                }
                left/=2;
                right/=2;
            }
            return sum;
        }
        
**********************************************

**********************************************

**12, HashMap, LinkedHashMap, TreeMap Problem**
**********************************************

```
12.1 (716) Max Stack
```

## Summary
Time Complexity: 

|               |   insertion   |   deletion    |     search    |
| ------------- | ------------- | ------------- | ------------- |
| HashMap       |      O(1)     |     O(1)      |      O(1)     |
| LinkedHashMap |      O(1)     |     O(1)      |      O(1)     |
| TreeMap       |    O(logn)    |    O(logn)    |     O(logn)   |

**13, Graph Problem**
**********************************************

```
13.1 (716) Max Stack 
```

## Summary



