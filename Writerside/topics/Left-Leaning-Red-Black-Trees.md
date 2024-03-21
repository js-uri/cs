# Left-Leaning Red-Black Trees

<show-structure for="chapter,procedure" depth="2"/>

<tabs>
    <tab title="Intro">
        <video src="https://youtu.be/qvZGUFHWChY?feature=shared" preview-src="intro_yt.jpeg" width="900" 
mini-player="true"/>
    </tab>
    <tab title="Rotations">
        <video src="https://youtu.be/95s3ndZRGbk?feature=shared" preview-src="rotations_yt.jpeg" width="705" mini-player="true"/>
    </tab>
    <tab title="Insertion {Strategy}">
        <video src="https://youtu.be/5IBxA-bZZH8?feature=shared" preview-src="insertions_strat_yt.png" width="705" 
mini-player="true"/>
    </tab>
    <tab title="Insertion {Examples}">
        <video src="https://youtu.be/A3JZinzkMpk?feature=shared" preview-src="insertions_ex_yt.jpeg" width="705" mini-player="true"/>
    </tab>
    <tab title="Deletions">
        <video src="https://youtu.be/lU99loSvD8s?feature=shared" preview-src="deletions_yt.png" width="705" mini-player="true"/>
    </tab>
    <tab title="Deletion Fixes">
        <video src="https://youtu.be/iw8N1_keEWA?feature=shared" preview-src="delete_fixes_yt.png" width="705" mini-player="true"/>
    </tab>
</tabs>



## Definition

<note>
<p>A left-leaning red-black tree is a self-balancing binary search tree that maintains balance through the 
use of coloring and rotation operations. In this variation of red-black trees, every edge is either red or black, and it satisfies the red-black properties, with an additional constraint that no right child of a node can be red.</p>
</note>



### Use Cases

<table>
<tr>
<td>
<procedure>
<img src="https://user-images.githubusercontent.com/38887077/76482821-4ec64780-6450-11ea-862e-da506f5cdae2.png" 
alt="image"/>
<p><b>Database Indexing</b></p>
<step>Efficient for indexing in databases, facilitating quick search and retrieval operations<br/></step>
</procedure>
</td>
<td>
<procedure>
<img src="https://www.bogotobogo.com/cplusplus/images/memoryallocation/memory_allocation_delete.png" alt="image"/>
<p><b>Memory Allocation</b></p>
<step>employed in memory allocators to maintain a balanced structure, optimizing memory access times</step>
</procedure>
</td>
<td>
<procedure>
<img src="https://smbmatters.files.wordpress.com/2012/01/network_routing.jpg?w=630" alt="image"/>
<p><b>Network Routing</b></p>
<step>Used in routing tables for efficient IP address lookup in network routers<br/><br/></step>
</procedure>
</td>
</tr>
<tr colspan="3">
<td>

Symbol tables:   
- Left-leaning red-black trees are often used to implement symbol tables in programming languages and compilers. The efficient search and insertion operations of red-black trees make them well-suited for storing and managing symbol tables.  
  
File systems:   
- Left-leaning red-black trees can be used to implement file systems, where the tree structure is used to organize and manage the files and directories within the system. The self-balancing property of red-black trees helps maintain a balanced and efficient file system structure.   
    
Compiler optimization:   
- Left-leaning red-black trees are used in compiler optimization techniques to efficiently store and manage intermediate representations of code. The balanced nature of red-black trees helps optimize the compilation process and improve overall performance.
</td>
</table>


### Advantages &amp; Disadvantages

<table>
<tr>
<td>Advantages</td>
<td>Disadvantages</td>
</tr>
<tr>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Simpler Maintenance">
The left-leaning property simplifies the tree structure compared to traditional red-black trees
</def>
<def title="Balanced Operations">
Maintains a balanced structure, ensuring efficient search, insert, and delete operations
</def>
</deflist>
</td>
<td>

<deflist collapsible="true" default-state="collapsed">
<def title="Increased Memory Usage">
The additional color bit for each node increases memory overhead
</def>
<def title="Complex Implementation">
Implementing left-leaning red-black trees can be more complex than simpler data 
structures
</def>
</deflist>
</td>
</tr>
</table>


## Implementation

### 2-3 Tree from BST

<procedure>
<tabs>
<tab title="Challenge">

<br/>

**How to represent a 3-node?**

![](llrb_challenge.jpeg)
{thumbnail="true" width="900"}
</tab>
<tab title="Approach 1">

<br/>

<deflist collapsible="true">
<def title="Regular BST">

- No way to tell a 3-node from a 2-node
- Can’t (uniquely) map from BST back to 2-3 tree
</def>
</deflist>

![](llrb_approach1.jpeg)
{thumbnail="true" width="900"}
</tab>
<tab title="Approach 2">

<deflist collapsible="true">
<def title="Regular BST w/ red 'glue' nodes">

- Wastes space for extra node
- Messy code
</def>
</deflist>

![](llrb_approach2.jpeg)
{thumbnail="true" width="900"}
</tab>
<tab title="Approach 3">

<deflist collapsible="true">
<def title="Regular BST w/ red 'glue' links">

- Widely used in practice
- Arbitrary restriction: red links lean left
</def>
</deflist>

![](llrb_approach3.jpeg)
{thumbnail="true" width="900"}
</tab>
<tab title="1-1 Correspondence">

![](llrb_1to1.jpeg)
{thumbnail="true" width="900"}
</tab>
</tabs>
</procedure>

<note>
<p><b>Structure</b></p>
<p>A left-leaning red-black tree is a type of self-balancing binary search tree that maintains the following properties</p>

- Every node is colored either red or black  
- The root node is always black  
- Every leaf (null node) is considered black  
- If a node is red, both its children are black  
- Every path from a node to its descendant leaves contains the same number of black nodes  
</note>


### Defining LLRB Trees (w/o 2-3 reference)

<table>
<tr>
<td>

**A BST such that:**

- No node has two red links connected to it
- Red links lean left
- Every path from root to null has the same number of black links
</td>
</tr>
<tr>
<td>

![](llrb_img.jpeg)
{thumbnail="true" width="900"}

</td>
</tr>
</table>


### Left-Leaning Red-Black Tree Rules

<note>
<p><b>Rules</b></p>

- The color of every new node inserted is Red &amp;&amp; The root node is always Black  
- The color of every new node inserted is Red  
- Every NULL child of a node is Black  
- If a node has a Red child and a left Black child (or NULL child because all NULLS are Black), left rotate the Node and swap the colors of the current Node and its left child to keep rule 2 consistent, i.e. the new Node must be Red.  
</note>

<note>
The color of every new node inserted is Red &amp;&amp; The root node is always Black

![](llrb_root_node.jpeg)

Every NULL child of a node is Black

![](llrb_null_child.jpeg)

If a node has a Red child and a left Black child (or NULL child because all NULLS are Black), left rotate the Node and swap the colors of the current Node and its left child to keep rule 2 consistent, i.e. the new Node must be Red.

![3-node](llrb_3_node.jpeg)

![](llrb_representation.jpeg)
</note>


### Representing LLRB Trees

<table>
<tr>
<td>
Each node is pointed to by precisely one link (from its parent) 
 can encode color of links in nodes
</td>
</tr>
<tr>
<td>

```c++
// LLRB node
private static final boolean RED = true;
private static final boolean BLACK = false;

private class Node {
    Key key;
    Value val;
    Node left, right;
    boolean color;
}
```

```c++
// handling the color of the link
private boolean isRed(Node x) {
    if (x == null) return false;
    return x.color == RED;
}
```
</td>
</tr>
</table>

<table>
<tr>
<td colspan="5">
Succession
</td>
</tr>
<tr>
<td>

![](llrb_road1.jpeg)
{thumbnail="true" width="900"}
</td>
<td>

![](llrb_road2.jpeg)
{thumbnail="true" width="900"}
</td>
<td>

![](llrb_road3.jpeg)
{thumbnail="true" width="900"}
</td>
<td>

![](llrb_road4.jpeg)
{thumbnail="true" width="900"}
</td>
<td>

![](llrb_road5.jpeg)
{thumbnail="true" width="900"}
</td>
</tr>
</table>


## Operations

<procedure>
<tabs>
<tab title="Overview">



**Basic strategy**

- Maintain 1-1 correspondence with 2-3 trees

<br/>

**During internal operations, maintain**

- Symmetric order.
- Perfect black balance.
- [ but not necessarily color invariants ]

<br/>

To restore color invariants: perform rotations and color flips


</tab>
<tab title="Left Rotation">

<table>
<tr>
<td>

```c++
private Node rotateLeft(Node h) {
    Node x = h.right;
    h.right = x.left;
    x.left = h;
    x.color = h.color;
    h.color = RED;
    return x;
}
```

</td>
<td>

![](llrb_right_lean.jpeg)
{thumbnail="true" width="900"}

<br/>

![](llrb_left_rotate.jpeg)
{thumbnail="true" width="900"}

</td>
</tr>
</table>

</tab>
<tab title="Right Rotation">

<table>
<tr>
<td>

```c++
private Node rotateRight(Node h) {
    Node x = h.left;
    h.left = x.right;
    x.right = h;
    x.color = h.color;
    h.color = RED;
    return x;
}
```

</td>
<td>

![](llrb_2_left_lean.jpeg)
{thumbnail="true" width="900"}

<br/>

![](llrb_right_rotate.jpeg)
{thumbnail="true" width="900"}

</td>
</tr>
</table>

</tab>
<tab title="Color Flip">

<table>
<tr>
<td>

```c++
private void flipColors(Node h) {
    h.color = RED;
    h.left.color = BLACK;
    h.right.color = BLACK;
}
```

</td>
<td>

![](llrb_left_right_lean.jpeg)
{thumbnail="true" width="900"}

<br/>

![](llrb_invert.jpeg)
{thumbnail="true" width="900"}

</td>
</tr>
</table>

</tab>
</tabs>
</procedure>


### Search

<table>
<tr>
<td>

![](llrb_tree.jpeg)

</td>
</tr>
<tr>
<td>

Search is the same as for BST (ignore color)

```text
Search(Node, key)
    if Node is NULL
        return NULL
    if key == Node.key
        return Node
    if key < Node.key
        return Search(Node.left, key)
    else
        return Search(Node.right, key)
```

</td>
</tr>
</table>


### Insertion

<procedure>
<tabs>
<tab title="Insertion Strategy">

```text
- Insert new node as red
    - if new node is root, flip color

- If right child is red, rotate left

- If left child is red and 
    - left-left child is red, rotate right 
    - right child is red, rotate left
    - right-right child is red, rotate left

- If both left and right children are red, flip colors
```
</tab>
<tab title="Insert 4">

![](llrb_insert_4.jpeg)
{thumbnail="true" width="900"}

</tab>
<tab title="Insert 6">

![](llrb_insert_6.jpeg)
{thumbnail="true" width="900"}

</tab>
</tabs>
</procedure>

### Deletion

<procedure>
<tabs>
<tab title="Deletion Strategy">

```text
If the node to be deleted has 
    - no children, simply remove it and update the parent node.
    - only one child, replace the node with its child.
    - two children, then replace the node with its in-order successor, which is the leftmost node in the right subtree. Then delete the in-order successor node as if it has at most one child.
After the node is deleted, the red-black properties might be violated. To restore these properties, some color changes and rotations are performed on the nodes in the tree. The changes are similar to those performed during insertion, but with different conditions.
```

</tab>
<tab title="Delete 40">

<table>
<tr>
<td>

![](llrb_delete1.jpeg)
{thumbnail="true" width="900"}

```text
Let the `nodeToBeDeleted` be 40  
  
And save the color of `nodeToBeDeleted` in `originalColor`  
```
</td>
<td>

![](llrb_delete2.jpeg)
{thumbnail="true" width="900"}

```text
Assign the right child of `nodeToBeDeleted` to `x`
```
</td>
<td>

![](llrb_delete3.jpeg)
{thumbnail="true" width="900"}

```text
Transplant `nodeToBeDeleted` with `x`
```
</td>
</tr>
<tr>
<td colspan="3">

```text

Else if the right child of `nodeToBeDeleted` is `NULL`  
    - Assign the left child of `nodeToBeDeleted` into `x`  
    - Transplant `nodeToBeDeleted` with `x`  
  
Else  
    - Assign the minimum of right subtree of `noteToBeDeleted` into `y`  
    - Save the color of `y` in `originalColor`  
    - Assign the rightChild of `y` into `x`  
    - If `y` is a child of `nodeToBeDeleted`, then set the parent of `x` as `y`  
    - Else, transplant `y` with `rightChild` of `y`  
    - Transplant `nodeToBeDeleted` with `y`  
    - Set the color of `y` with `originalColor`    
  
If the `originalColor` is BLACK, call `DeleteFix(x)`  
```

</td>
</tr>
</table>
</tab>
<tab title="Maintain Color">

Eliminating Red-Red Violations: 
- Red-red violations occur when there are consecutive red nodes in the tree. These violations are not allowed in a left-leaning red-black tree. The function should handle cases where red nodes are siblings or uncle-nephew pairs and perform necessary rotations and color flips to eliminate the violations.

<table>
<tr>
<td>

![](llrb_delete_easy.jpeg)
{thumbnail="true" width="900"}
</td>
<td>

![](llrb_delete_choice.jpeg)
{thumbnail="true" width="900"}
</td>
</tr>
</table>

Restoring Balance: 
- After fixing red-red violations, you need to ensure that the tree remains balanced according to the left-leaning red-black tree properties. This may involve performing rotations and color changes to maintain the balance and preserve the left-leaning property.

![](llrb_delete_any.jpeg)
{thumbnail="true" width="900"}

</tab>
</tabs>
</procedure>


## Visualizations | n = 255

<procedure>
<tabs>
<tab title="Random">

```tex
height\ = 9
```
<br/>
```tex
average\ depth\ = 6.3
```

<br/>

![](llrb_random.jpeg)
{thumbnail="true" width="900"}
</tab>
<tab title="Ascending">

```tex
height\ = 7
```
<br/>
```tex
average\ depth\ = 6.0
```

<br/>

![](llrb_ascending.jpeg)
{thumbnail="true" width="900"}
</tab>
<tab title="Descending">

```tex
height\ = 13
```
<br/>
```tex
average\ depth\ = 6.5
```

<br/>

![](llrb_descending.jpeg)
{thumbnail="true" width="900"}
</tab>
</tabs>

</procedure>


## Balancing

<table>
<tr>
<td>

**Proportion**  

<br/>

```tex
\bullet \text{ Height of corresponding 2-3 tree is: } log_2\ n
```

</td>
</tr>
<tr>
<td>

**Proof**

```tex
\bullet \text{ Black height = height of corresponding 2-3 tree } \le log_2\ n \\
```
<br/>

```tex
\bullet \text{ Never two red links in a row } \\ 
```
<br/>

```tex
\ \ \ \ \text{ $\Rightarrow$  height of LLRB tree } \le (2 * black\ height) + 1 \le 2\ log_2\ n  \\
```

```tex
\bullet \text{[A slightly more refined argument show } height\ \le 2\ log\ n]
```

</td>
</tr>
<tr>
<td>

![](llrb_balance.jpeg)
{thumbnail="true"}

```tex 
height\ \le 2\ log_2\ n
```

</td>
</tr>

</table>



## Complexity

<procedure>

![Time Complexity Comparison Chart](llrb_complexity.jpeg)

</procedure>














































