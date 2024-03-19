# 2-3 Trees

<video src="https://youtu.be/yExQKCYTC9E" preview-src="2-3-4_video_img.jpeg" controls="true" width="900" />


## Definition

<table>
<tr>
<td>

**Purpose**

<br/>
2-3 trees are a type of self-balancing tree data structure that can be used to implement a variety of algorithms and data structures. They are similar to binary search trees, but have the advantage of better balancing, which ensures that the height of the tree remains small and operations such as insertions, deletions, and searches are efficient.  
  
<br/>
Here are some reasons why 2-3 trees can be useful:  

<br/>
<deflist collapsible="true">
<def title="self-balancing">
Unlike ordinary binary search trees, 2-3 trees are designed to be self-balancing. This means that they automatically adjust their structure as data is added or removed, to ensure that the tree remains balanced and efficient.
</def>
<def title="better performance">

2-3 trees guarantee worst-case performance of `O(log n)` for most operations, including insertions, deletions, and searches. This makes them useful in applications where worst-case performance is important.

</def>
<def title="efficient range queries">
Because 2-3 trees are balanced, they can efficiently perform range queries (i.e., finding all values within a given range). This can be useful in a variety of applications, such as database indexing.
</def>
<def title="space efficient">
2-3 trees are space efficient, as they do not require additional pointers or overhead to maintain balance. This makes them a good choice for applications where memory usage is a concern.
</def>
</deflist>

<br/>
Overall, 2-3 trees are a versatile and efficient data structure that can be used in a variety of applications where balanced trees are needed.

</td>
<td>

**Uses**

<br/>
Here are some examples of programs that would benefit from using 2-3 trees:

<br/>
<deflist collapsible="true">
<def title="Database systems">
2-3 trees are commonly used in database systems to implement indexes, which allow for efficient searching and retrieval of data. They are particularly useful for range queries, where the goal is to find all values within a given range.
</def>
<def title="File systems">

File systems often use 2-3 trees to store and manage directory structures, as well as to maintain file metadata such as permissions, timestamps, and other attributes.
</def>
<def title="Compiler symbol tables">

Compiler symbol tables, which store information about variables, functions, and other program elements, can benefit from using 2-3 trees to efficiently search and retrieve information.
</def>
<def title="Memory management">

2-3 trees can be used in memory management systems to efficiently allocate and deallocate memory, as well as to maintain data structures such as free lists and memory maps.
</def>
<def title="Network routing tables">

Network routing tables, which store information about network addresses and routes, can benefit from using 2-3 trees to efficiently search and retrieve routing information.
</def>
</deflist>

<br/>
Overall, 2-3 trees can be used in any program that needs to efficiently store and search large amounts of data, and where balanced trees are needed to ensure good worst-case performance.

</td>
</tr>
</table>


## Components

<table>
<tr>
<td colspan="6">

![2-3-4 Nodes](2-3-4_nodes.jpeg)
</td>
</tr>
<tr>
<td colspan="2">

<deflist collapsible="true">
<def title="2-node">
A 2-node is a node in a 2-3 tree that contains one data item and two child nodes. The data item is stored in the node, and the child nodes are stored in the left and right pointers. The left child contains data items that are less than the node's data item, and the right child contains data items that are greater than the node's data item.
</def>
</deflist>

</td>
<td colspan="2">

<deflist collapsible="true">
<def title="3-node">
A 3-node is a node in a 2-3 tree that contains two data items and three child nodes. The data items are stored in the node, and the child nodes are stored in the left, middle, and right pointers. The left child contains data items that are less than the node's low data item, the middle child contains data items that are between the node's low and high data items, and the right child contains data items that are greater than the node's high data item.
</def>
</deflist>

</td>
<td colspan="2">

<deflist collapsible="true">
<def title="4-node">
A 4-node is a node in a 2-3 tree that contains three data items and four child nodes. The data items are stored in the node, and the child nodes are stored in the left, middle-left, middle-right, and right pointers. The left child contains data items that are less than the node's low data item, the middle-left child contains data items that are between the node's low and middle data items, the middle-right child contains data items that are between the node's middle and high data items, and the right child contains data items that are greater than the node's high data item.
</def>
</deflist>

</td>
</tr>
<tr>
<td colspan="3">

**Symmetric order**

<br/>

In a 2-3 tree, the data items in each node are stored in symmetric order. This means that the left child contains data items that are less than the node's low data item, the middle child contains data items that are between the node's low and high data items, and the right child contains data items that are greater than the node's high data item. This symmetric order ensures that the tree remains balanced and efficient.

</td>
<td colspan="3">

**Balanced tree**

<br/>

A 2-3 tree is a balanced tree, which means that the height of the tree is kept small and the tree remains efficient. This is achieved by ensuring that each node in the tree contains the correct number of data items and child nodes, and that the tree is symmetrically ordered. This balance ensures that operations such as insertions, deletions, and searches are efficient.

</td>
</tr>
<tr>

<td colspan="6">

![Splitting a 4-node](temp_4_node.jpeg)
{width="900"}
</td>
</tr>
</table>


## Operations

### Search

<table>
<tr>
<td colspan="2">

**Rules**

- Searching in a 2-3 tree follows the same process as in a binary search tree, but with additional comparisons for 3-nodes.
- *_Note: when inserting a key, the tree ensures that it is placed in the correct position to maintain the rules of a 2-3 tree, potentially splitting and rearranging nodes as needed to maintain balance._*
</td>
</tr>
<tr>
<td>

1. Start at the root of the tree.
2. Compare the key to be searched with the keys in the current node.
   3. If the key is equal to any of the keys in the node, return the value associated with that key.
   4. If the key is less than the smallest key in the node, move to the left child node.
   5. If the key is greater than the largest key in the node, move to the right child node.
   6. If the key is between the smallest and largest keys in the node, move to the middle child node.
   7. Repeat step 2 until a leaf node is reached.

   {type="bullet"}
8. If the key is found in the leaf node, return the value associated with the key.
9. If the key is not found in the leaf node, return that the key is not in the tree.
10. The search process is complete.
11. Return.

</td>
<td>

![2-3-4 Search](2-3-4_search.jpeg)
{width="900" thumbnail="true"}

</td>
</tr>
</table>


### Insert

<table>
<tr>
<td colspan="2">

**Rules**

- When inserting a key into a 2-3 tree, the tree maintains its balance by performing rotations and node splits as necessary.
- If inserting a key causes a node to have more than two keys (creating a 4-node), the node splits, and the middle key moves up to the parent node, effectively splitting the node into two 2-nodes or creating a new 3-node in the parent if it was already a 3-node.
</td>
</tr>
<tr>
<td>

1. Start at the root of the tree.
2. Compare the new key with the keys in the current node.
   3. If the new key is equal to any of the keys in the node, update the value associated with that key.
   4. If the new key is less than the smallest key in the node, move to the left child node.
   5. If the new key is greater than the largest key in the node, move to the right child node.
   6. If the new key is between the smallest and largest keys in the node, move to the middle child node.
   7. Repeat step 2 until a leaf node is reached.

    {type="bullet"}
8. Insert the new key and value into the leaf node.
   9. If the leaf node is full (contains 3 keys), split the node into two nodes with 2 keys each.
   10. If the parent of the leaf node is full, split the parent node as well.
       11. Continue splitting up the tree until the root node is reached.

       {type="bullet"}
   12. If the root node is full, split the root node into two nodes with 2 keys each and update the root.

    {type="bullet"}
13. The insertion process is complete.
14. Return.

</td>
<td>

<tabs>
<tab title="Case 1">

**Insert in a node with only one data element**

<br/>

![2-3-4 Insert 1](2-3-4_insert_case1.jpeg)
{width="900" thumbnail="true"}
</tab>
<tab title="Case 2">

**Insert in a node with two data elements whose parent contains only one data element**

<br/>

![2-3-4 Insert 2.1](2-3-4_insert_case2_1.jpeg)
{width="300" thumbnail="true"}

<br/>

![2-3-4 Insert 2.2](2-3-4_insert_case2_2.jpeg)
{width="300" thumbnail="true"}

<br/>

![2-3-4 Insert 2.3](2-3-4_insert_case2_3.jpeg)
{width="300" thumbnail="true"}

</tab>
<tab title="Case 3">

**Insert in a node with two data elements whose parent contains two data elements**

<br/>

![2-3-4 Insert 3.1](2-3-4_insert_case3_1.jpeg)
{width="300" thumbnail="true"}

<br/>

![2-3-4 Insert 3.2](2-3-4_insert_case3_2.jpeg)
{width="300" thumbnail="true"}

<br/>

![2-3-4 Insert 3.3](2-3-4_insert_case3_3.jpeg)
{width="300" thumbnail="true"}

<br/>

![2-3-4 Insert 3.4](2-3-4_insert_case3_4.jpeg)
{width="300" thumbnail="true"}

</tab>
</tabs>

</td>
</tr>
</table>

### Delete

<table>
<tr>
<td colspan="2">

**Rules**

- When deleting a key, the tree may undergo node merges or redistributions to maintain balance.
- If a node has fewer than two keys after deletion, it may need to borrow a key from a sibling node or merge with a sibling node to maintain the properties of a 2-3 tree.

</td>
</tr>
<tr>
<td colspan="2">

**Considerations**

- To delete a value, it is replaced by its in-order successor and then removed.
- If a node is left with less than one data value then two nodes must be merged together.
- If a node becomes empty after deleting a value, it is then merged with another node.

</td>
</tr>
<tr>
<td>

1. Start at the root of the tree.
2. Compare the key to be deleted with the keys in the current node.
   3. If the key is equal to any of the keys in the node, delete the key and value from the node.
   4. If the key is less than the smallest key in the node, move to the left child node.
   5. If the key is greater than the largest key in the node, move to the right child node.
   6. If the key is between the smallest and largest keys in the node, move to the middle child node.
   7. Repeat step 2 until a leaf node is reached.
   
    {type="bullet"}
8. If the leaf node contains more than one key, delete the key and value from the node.
9. If the leaf node contains only one key, find the nearest sibling node with more than one key.
10. If the nearest sibling node has more than one key, borrow the smallest key from the sibling node and replace the key in the parent node.
11. If the nearest sibling node has only one key, merge the leaf node with the sibling node and delete the key from the parent node.
12. Continue merging up the tree until the root node is reached.
13. If the root node contains only one key, delete the key and update the root.
14. The deletion process is complete.
15. Return.

</td>
<td>

<tabs>
<tab title="Starting tree">

![](2-3-4_delete_start.jpeg)
{width="900" thumbnail="true"}

</tab>
<tab title="69">

**Swap it with its in-order successor, that is, 72. 69 now comes in the leaf node. Remove the value 69 from the leaf node.**

<br/>

![](2-3-4_delete_69.jpeg)
{width="900" thumbnail="true"}

</tab>
<tab title="72">

**72 is an internal node**

<br/>

To delete this value swap 72 with its in-order successor 81 so that 72 now becomes a leaf node. Remove the value 72 from the leaf node.

<br/>

![](2-3-4_delete_72_1.jpeg)
{width="900" thumbnail="true"}

<br/>

Now there is a leaf node that has less than 1 data value thereby violating the property of a 2-3 tree. So the node must be merged. To merge the node, pull down the lowest data value in the parent’s node and merge it with its left sibling.

<br/>

![](2-3-4_delete_72_2.jpeg)
{width="900" thumbnail="true"}

</tab>
<tab title="99">

**99 is present in a leaf node, so the data value can be easily removed**

<br/>

![](2-3-4_delete_99_1.jpeg)
{width="900" thumbnail="true"}

<br/>

Now there is a leaf node that has less than 1 data value, thereby violating the property of a 2-3 tree. So the node must be merged. To merge the node, pull down the lowest data value in the parent’s node and merge it with its left sibling.

<br/>

![](2-3-4_delete_99_2.jpeg)
{width="900" thumbnail="true"}

</tab>
<tab title="81">

**81 is an internal node**

<br/>

To delete this value swap 81 with its in-order successor 90 so that 81 now becomes a leaf node. Remove the value 81 from the leaf node.

<br/>

![](2-3-4_delete_81_1.jpeg)
{width="900" thumbnail="true"}

<br/>

Now there is a leaf node that has less than 1 data value, thereby violating the property of a 2-3 tree. So the node must be merged.

To merge the node, pull down the lowest data value in the parent’s node and merge it with its left sibling.

<br/>

![](2-3-4_delete_81_2.jpeg)
{width="900" thumbnail="true"}

<br/>

As internal node cannot be empty. So now pull down the lowest data value from the parent’s node and merge the empty node with its left sibling

<br/>

![](2-3-4_delete_81_3.jpeg)
{width="900" thumbnail="true"}

</tab>
</tabs>

</td>
</tr>
<tr>
<td colspan="2">

**Example**

![](2-3-4_delete_viz.jpeg)
{width="900" thumbnail="true"}
</td>
</tr>
</table>


### Consider

<procedure>

The three sets are identical minus their order… does it matter? [Try them](https://yongdanielliang.github.io/animation/web/24Tree.html) and see…

```tex
\begin {align*}
tree 1 & = \{ 13, 5, 18, 16, 19, 24, 1, 10, 3, 8, 12 \} \\
tree 2 & = \{ 24, 19, 12, 16, 5, 13, 1, 10, 8, 3, 18 \} \\
tree 3 & = \{ 19, 10, 18, 12, 13, 24, 1, 5, 3, 8, 16 \} \\
\end {align*}
```

*_Note: the link will show you the outcomes for a 2-3-4 tree, not a 2-3 tree._*

</procedure>


### Performance

<table>
<tr>
<td>

**Perfect balance**

<br/>

A 2-3 tree is a balanced tree, which means that the height of the tree is kept small and the tree remains efficient. This is achieved by ensuring that each node in the tree contains the correct number of data items and child nodes, and that the tree is symmetrically ordered. This balance ensures that operations such as insertions, deletions, and searches are efficient.

</td>
</tr>
<tr>
<td>

![](2-3-4_perfect_balance.jpeg)
{width="900" thumbnail="true"}

</td>
</tr>
<tr>
<td>

**Tree height**

<br/>

- min : 
  ```tex
    log_3 n \approx 0.631\ log_2\ n
  ```
- max : 
  ```tex
    log_2\ n
  ```
- Between 12 and 20 for a million nodes
- Between 18 and 30 for a billion nodes


</td>
</tr>
<tr>
<td>

<deflist collapsible="true">
<def title="Bottomline">
Guaranteed logarithmic performance for search and insert operations.
</def>
</deflist>
</td>
</tr>
</table>


### Complexity

<procedure>

![](2-3-4_complexity.jpeg)
{width="900" thumbnail="true"}

*_Note: hidden constant `c` is large_*
</procedure>


### Implementation

<procedure>

**Direct implementation is complicated, because**

- Maintaining multiple node types is cumbersome
- Need multiple compares to move down tree
- Need to move back up the tree to split 4-nodes
- Large number of cases for splitting

<br/>

```c++
// 2-3 tree node

struct Node {
    int data1;
    int data2;
    Node* left;
    Node* middle;
    Node* right;
};

// 2-3 tree class

class TwoThreeTree {
public:
    TwoThreeTree();
    void insert(int data);
    void remove(int data);
    bool search(int data);
    void print();
    
private:
    Node* root;
    void insert(Node* node, int data);
    void split(Node* node);
    void remove(Node* node, int data);
    void removeLeaf(Node* node, int data);
    void removeInternal(Node* node, int data);
    void print(Node* node);
};
```

</procedure>


[//]: # (<deflist>)

[//]: # (<def title="visual">)

[//]: # ()
[//]: # (![]&#40;2-3-4_consider_viz_1.jpeg&#41;)

[//]: # ({width="900" thumbnail="true"})

[//]: # ()
[//]: # (</def>)

[//]: # (<def title="visual">)

[//]: # ()
[//]: # (![]&#40;2-3-4_consider_viz_2.jpeg&#41;)

[//]: # ({width="900" thumbnail="true"})

[//]: # ()
[//]: # (</def>)

[//]: # (<def title="visual">)

[//]: # ()
[//]: # (![]&#40;2-3-4_consider_viz_3.jpeg&#41;)

[//]: # ({width="900" thumbnail="true"})

[//]: # ()
[//]: # (</def>)

[//]: # (</deflist>)


