# File: lca.go

lca.go是一个Go语言编写的命令行工具，它的作用是计算给定两个节点的最近公共祖先（Lowest Common Ancestor，简称LCA）。

LCA算法是计算树中两个节点的最近公共祖先的一种经典算法，它在计算树中两个节点的距离、计算树的直径等算法中都有重要应用。

lca.go实现了两种计算LCA的算法：倍增法和Tarjan法。倍增法是一种基于二进制拆分时间复杂度为O(N log N)的算法，而Tarjan法是一种基于并查集时间复杂度为O(N + Q)的算法，其中N为节点个数，Q为查询次数。lca.go还支持从文件中读取指定格式的树信息。

除此之外，lca.go还提供了一些命令行选项，可以指定输入文件、输出文件、计算方式等，方便用户使用。




---

### Structs:

### lcaRange

lcaRange是一个结构体，代表一个用于最近公共祖先问题的线段树结构。具体来说，它允许我们在一棵树上进行区间查询，找到两个节点之间的最近公共祖先。

lcaRange结构体包含以下重要成员变量：

- graph：代表输入的树。它是一个邻接表，可以使用graph[x]来获取节点x的所有邻居节点。
- first：代表每个节点在欧拉序列中第一次出现的位置。
- euler：代表存储欧拉序列。
- height：代表每个节点在欧拉序列中的高度。
- depth：代表每个节点的深度。
- sparseTable：用于预处理的稀疏表结构，用于快速找到区间中的最小值。

lcaRange结构体中最重要的成员函数是LCA和preprocess。preprocess函数在构造线段树之前，对树进行预处理，计算出欧拉序列、欧拉序列中每个节点第一次出现的位置、每个节点的深度，以及用于快速寻找区间最小值的稀疏表。LCA函数用于查询区间内两个节点的最近公共祖先。

使用lcaRange数据结构，我们可以很快地回答类似于"树上两个节点的路径中权值最小的边是什么?"或者"树上两个节点的距离是多少?"等问题。



### lcaRangeBlock

lcaRangeBlock是用于存储LCA区间查询算法中的预处理数据的数据结构。LCA区间查询是指在一棵有根树中，给定两个节点u和v，查询它们在树上的最近公共祖先，同时还需要支持查询它们之间路径上的所有节点。

LCA区间查询算法的思路是基于倍增算法和分块算法，将树上节点的深度信息利用倍增算法预处理出来，并将每个块中深度最大值所在的节点作为该块的代表节点，存储到lcaRangeBlock的数据结构中。具体地，算法将每个块视为一个黑盒，预处理出每个黑盒的区间内的最大深度，以及跨越黑盒边界的所有可能的LCA节点，并存储到lcaRangeBlock中。

在使用LCA区间查询算法进行查询时，我们会将查询区间分成若干个块，对于每个块，我们利用lcaRangeBlock中存储的信息快速计算出该块内的最近公共祖先，以及跨越块边界的所有可能的LCA节点。最后，将每个块内的答案进行合并即可得到整个查询区间的结果。

因此，lcaRangeBlock在LCA区间查询算法中扮演了预处理数据的角色，可以帮助我们快速计算出每个块内的LCA节点及其深度信息，以及块与块之间可能的LCA节点。



## Functions:

### makeLCArange

makeLCArange函数现在已被删除，但它的作用是构建给定二叉搜索树中每个节点的最近公共祖先（LCA）的范围表。这个函数实现了一种高效的算法，它使用递归和二分查找来构建LCA范围表。

具体来说，makeLCArange函数的输入是一个指向二叉搜索树根节点的指针。该函数首先使用深度优先搜索（DFS）遍历该树，以构建一个节点列表。然后，它使用这个列表来构建一个数组，其中每个元素表示相应节点的值，该值是一组LCA范围。该数组的长度等于节点列表的长度。

最后，makeLCArange函数使用递归和二分查找构建LCA范围表。递归过程从根节点开始，分别对根节点的左子树和右子树进行递归。对于每个节点，它的LCA范围是其左子树和右子树的LCA范围的并集，再加上该节点自身的值。递归过程在叶节点处结束。

makeLCArange函数返回一个指向包含LCA范围表的数组的指针。这个数组中的每个元素对应于给定二叉搜索树的每个节点，对应元素中的值表示节点的LCA范围。



### find

lca.go中的find函数是用于在二叉树中查找节点值为val的节点的。它通过递归的方式从根节点开始遍历二叉树，如果当前节点的值等于val，则返回该节点；如果小于val，则继续遍历节点的右子树；如果大于val，则继续遍历节点的左子树。

在LCA算法中，需要用到find函数来查找p和q节点在二叉树中的位置，并确定它们的最近公共祖先节点。具体的实现过程如下：

首先，通过find函数查找p和q节点在二叉树中的位置。如果有在二叉树中不存在p或q节点，则返回nil，表示无法找到它们的最近公共祖先。

接着，使用递归的方式从根节点开始遍历二叉树。如果当前节点的值在p和q节点的值之间，则说明当前节点就是它们的最近公共祖先节点；如果当前节点的值大于p和q节点的值，就继续遍历当前节点的左子树；如果当前节点的值小于p和q节点的值，则继续遍历当前节点的右子树。

最终，找到的最近公共祖先节点就是要返回的结果。

总之，find函数是LCA算法中非常重要的一部分，它通过查找二叉树中的节点来确定p和q节点的位置，以及它们的最近公共祖先节点。


