# Search Trees (Binary & K-ary)

<show-structure for="chapter,procedure" depth="2"/>

<video src="https://youtu.be/GzJoqJO1zdI?feature=shared" preview-src="binary-tree-1-search.gif" width="700"/>



## Definitions

<table>
<tr>
<td>
<note>
    <p>A Binary Search Tree (BT) is a fundamental data structure in computer science, commonly used for organizing and 
searching data efficiently. It is a binary tree where each node has at most two children: a left child and a right 
child. The key property of a BST is that the values of nodes in the left subtree are less than or equal to the value of the current node, and the values of nodes in the right subtree are greater than the current node. This property makes BSTs especially useful for efficient searching and sorting of data.</p>
    <img src="https://www.chrislaux.com/android-chrome-192x192.png" alt="binary tree search"/>
</note>
</td>
<td>
<deflist collapsible="true">
    <def title="Search" collapsible="true" default-state="collapsed">
        Searching for a specific value in a BST is very efficient. You start at the root and compare the value you're looking for with the current node's value. If the value is smaller, you move to the left child; if it's larger, you move to the right child. This process continues until you find the desired value or reach a null (indicating that the value is not in the tree).
    </def>
    <def title="Insertion" collapsible="true" default-state="collapsed">
        To insert a new value into a BST, you traverse the tree similarly to searching. Once you find a null position where the new value should be, you create a new node and place it there, maintaining the BST property.
    </def>
    <def title="Deletion" collapsible="true" default-state="collapsed">
        Removing a value from a BST is more complex. There are various cases to consider, including when the node to be removed has zero, one, or two children. The operation involves finding the node, handling these cases, and rearranging the tree to preserve the BST property.
    </def>
    <def title="In-Order Traversal" collapsible="true" default-state="collapsed">
        One of the most common operations on a BST is in-order traversal. It visits all nodes in ascending order, making it useful for tasks like sorting the elements stored in the tree.
Min and Max: You can quickly find the minimum and maximum values in a BST by following the left (for minimum) or right (for maximum) child pointers until you reach a leaf node.
    </def>
    <def title="Min and Max" collapsible="true" default-state="collapsed">
        You can quickly find the minimum and maximum values in a BST by following the left (for minimum) or right (for maximum) child pointers until you reach a leaf node.
    </def>
    <def title="Balancing" collapsible="true" default-state="collapsed">
        The efficiency of a BST depends on its balance. An unbalanced tree, where one subtree is significantly deeper than the other, can degrade into a linked list, causing search and insertion to become inefficient. Self-balancing binary search trees like AVL trees or Red-Black trees automatically maintain balance during insertions and deletions.
    </def>
</deflist>
</td>
</tr>
<tr>
<td>
<note>
    <p>A k-ary search tree is a type of tree data structure used in computer science and information retrieval. It's an extension of the binary search tree (BST) where each node can have up to k children. In a binary search tree, each node has at most two children (a left child and a right child), while in a k-ary search tree, a node can have up to k children.</p>
    <img src="https://ucarecdn.com/7844a08e-27b8-4571-a88f-c7dedfa025c6/-/scale_crop/180x180/center/" alt="k-ary search tree search"/>
</note>
</td>
<td>
<deflist collapsible="true">
    <def title="Node Structure" collapsible="true" default-state="collapsed">
        Each node in the tree contains a key (or value) and a set of child pointers, typically ranging from 0 to k children.
    </def>
    <def title="Ordering Property" collapsible="true" default-state="collapsed">
        Like in a binary search tree, the nodes in a k-ary search tree are organized in such a way that for any given node, all the keys in its left subtree are less than its key, and all the keys in its right subtree are greater than its key. In a k-ary search tree, this ordering property extends to all its subtrees, where each subtree contains keys within specific value ranges.
    </def>
    <def title="Search Operation" collapsible="true" default-state="collapsed">
        The k-ary search tree is used for efficient searching and retrieval of data. When searching for a specific key, you start at the root and traverse the tree by comparing the key you're looking for with the keys in the nodes. Depending on the comparison, you proceed to the appropriate child subtree. This process continues until you find the key or reach a leaf node.
    </def>
    <def title="Insertion and Deletion" collapsible="true" default-state="collapsed">
        Insertion and deletion operations in a k-ary search tree maintain the ordering property. When inserting a new key, it is placed in an appropriate position in the tree to maintain the order. When deleting a key, the tree is adjusted to preserve the order as well.
    </def>
</deflist>
</td>
</tr>
</table>



### Tree Elements

<table>
<tr>
    <td>
    <procedure title="Elements" type="choices">
        <step>Node</step>
        <step>Data</step>
        <step>Right Child</step>
        <step>Left Child</step>
    </procedure>
    </td>
    <td>
        <img src="https://miro.medium.com/v2/resize:fit:1194/1*ziYvZzrttFYMXkkV9u66jw.png" alt="images/"/>
    </td>
</tr>
</table>



## Types of Binary & K-ary Trees

<tabs>
    <tab title="Types">
    <note>
        <img src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*CMGFtehu01ZEBgzHG71sMg.png" alt="types"/>
    </note>
    </tab>
    <tab title="Full">
    <note>
        <img src="https://miro.medium.com/max/1400/1*fh2By4u-SxTlt6u2xHqnCg.png" alt="full"/>
        <p>Full Binary Tree is a Binary Tree in which every node has 0 or 2 children.</p>
    </note>
    </tab>
    <tab title="Complete">
    <note>
        <img src="https://miro.medium.com/max/1400/1*M1qfRR59TR9-i4pmI-_Clg.png" alt="complete"/>
        <p>Complete Binary Tree has all levels completely filled with nodes except the last level and in the last level, all the nodes are as left side as possible.</p>
    </note>
    </tab>
    <tab title="Perfect">
    <note>
        <img src="https://miro.medium.com/max/1400/1*EgcvwUHXnmdOpbHQwgCknA.png" alt="perfect"/>
        <p>Perfect Binary Tree is a Binary Tree in which all internal nodes have 2 children and all the leaf nodes are at the same depth or same level.</p>
    </note>
    </tab>
    <tab title="Degenerate">
    <note>
        <img src="https://miro.medium.com/max/1400/1*m5BjLJeSrSGH4US-QXj4aA.png" alt="degenerate"/>
        <p>Degenerate Binary Tree is a Binary Tree where every parent node has only one child node.</p>
    </note>
    </tab>
    <tab title="Balanced">
    <note>
        <img src="https://miro.medium.com/max/1400/1*jSq-xjEZYytNDIBpZNQC2w.png" alt="balanced"/>
        <p>Balanced Binary Tree is a Binary tree in which height of the left and the right sub-trees of every node may differ by at most 1.</p>
    </note>
    </tab>
</tabs>

~ from [towardsdatascience.com](https://towardsdatascience.com/5-types-of-binary-tree-with-cool-illustrations-9b335c430254)

## Binary Search Tree

<table>
<tr>
<td>
<p>A <b>BST</b> has symmetric order</p><br/>
<p>Each node <code>x</code> in a BST has a key</p><br/>
<p>key <code>x</code></p><br/>
<procedure>
<p>For all nodes <code>y</code> in the left subtree of <code>x</code></p>
<step>key <code>y</code> &lt; key <code>x</code>**</step>
</procedure>
<procedure>
<p>for all nodes <code>y</code> in the right subtree of <code>x</code></p>
<step>key <code>y</code> &gt; key <code>x</code>**</step>
</procedure><br/>
<p><i>(**) Note: assume that the keys of a BST are pairwise distinct</i></p>
</td>
<td>
    <img src="https://i.pinimg.com/originals/4e/5a/00/4e5a00c98d5b46ed4cbf224ac11dc115.png" alt="images/"/>
</td>
</tr>
</table>

### Implementation : Classes

<table>
<tr>
<td>BST Node</td><td>BST Tree</td>
</tr>
<tr>
<td>
<code-block lang="c++">
    class BSTNode {
        private:
            int data;  
            BSTNode *left;  
            BSTNode *right;
        public:
            BSTNode(int d);
            ~BSTNode();
        friend class BSTree;
    };
</code-block>
</td>
<td>
<code-block lang="c++">
class BSTree{
    private:
        BSTNode *root;
        void destroy(BSTNode *p);
    public:
        BSTree();
        ~BSTree();
        void insert(int d);
        void remove(int d);  
        BSTNode *search(int d);
};
</code-block>
</td>
</tr>
</table>

### Implementation : Class Functions

<table>
<tr>
<td>
<procedure title="Search" type="choices">
    <p>Start at root node</p>
    <p>If the search key:</p>
    <step>matches current node’s key, return <b>found</b></step>
    <step>search key &lt; current node’s key : <b>search right</b> child</step>
    <step>search key &gt; current node’s key : <b>search left</b> child</step>
    <p>Stop when current node is NULL, return <b>not found</b></p>
</procedure>
</td>
<td><img src="https://www.happycoders.eu/wp-content/uploads/2021/06/binary-search-tree-insertion-800x467.png" 
alt="bst search"/></td>
</tr>
</table>

<table>
<tr>
<td>
<procedure title="Insert" type="choices">
    <p>Start at root node</p>
    <p>If the value is:</p>
    <step>smaller than current node's key : move to the left subtree</step>
    <step>larger than current node's key : move to the right subtree</step>
    <p>Repeat previous step, until a vacant spot is found</p>
    <p>Insert new node into vacant spot in tree</p>
</procedure>
</td>
<td><img src="https://www.happycoders.eu/wp-content/uploads/2021/06/binary-search-tree-insertion-800x467.png" 
alt="bst search"/></td>
</tr>
</table>

<table>
<tr>
<td>
<procedure title="Remove" type="choices">
    <p>Start at root node</p>
    <p>Search for node to remove; once found, if the node has:</p>
    <step><b>no children</b>; node is leaf and can be removed directly</step>
    <step><b>one child</b>; replace with its child node</step>
    <step><b>two children</b>; find the node’s successor (smallest value in the right subtree) or predecessor 
(largest value in the left subtree)<br/>Replace the node with its successor/predecessor and delete the 
successor/predecessor from its original position</step>
</procedure>
</td>
<td>
<tabs>
<tab title="leaf">
    <img src="algorithm-binary-tree-search_4.JPG" alt="bst remove leaf node"/>
</tab>
<tab title="one child">
    <img src="algorithm-binary-tree-search_5.JPG" alt="bst remove node with one child"/>
</tab>
<tab title="two children">
    <img src="algorithm-binary-tree-search_6.JPG" alt="bst remove node with two children"/>
</tab>
</tabs>
</td>
</tr>
</table>

<table>
<tr>
<td>
<procedure title="Traversals" type="choices">
    <p>Implications</p>
    <p>Traversal of a tree T is a systematic way of accessing, or “visiting,” all the positions of T . The specific action associated with the “visit” of a position p depends on the application of this traversal, and could involve anything from incrementing a counter to performing some complex computation for p.</p>
</procedure>
</td>
<td>
<img src="https://www.bogotobogo.com/GoLang/images/BinarySearchTree_BST/print_functions.png" alt="order types"/>
</td>
</tr>
<tr>
<td colspan="2">
<tabs>
    <tab title="preorder">
        <table>
        <tr>
        <td>
        <code-block lang="c++">
        // nodes of the BST are visited in a
        // pre-defined order before visiting
        // their child nodes.
        algorithm preorder (p) {
            if (p) {
                visit(p)
                preorder(p -> left)
                preorder(p -> right)
            }
        }
        </code-block>
        </td>
        <td><img src="https://sbme-tutorials.github.io/2020/data-structure-FALL/images/Tree06.png" alt="preorder"/></td>
        </tr>
        </table>
    </tab>
    <tab title="postorder">
        <table>
        <tr>
        <td>
        <code-block lang="c++">
        // nodes of the BST are visited in a 
        // pre-defined order after visiting 
        // their child nodes.
        algorithm postorder (p) {
            if (p) {
                postorder(p -> left)
                postorder(p -> right)
                visit(p)
            }
        }
        </code-block>
        </td>
        <td><img src="https://sbme-tutorials.github.io/2020/data-structure-FALL/images/Tree07.png" 
alt="postorder"/></td>
        </tr>
        </table>
    </tab>
    <tab title="inorder">
        <table>
        <tr>
        <td>
        <code-block lang="c++">
        // nodes of the BST are visited in
        // ascending order of their values.
        algorithm inorder (p) {
            if (p) {
                inorder(p -> left)
                visit(p)
                inorder(p -> right)
            }
        }
        </code-block>
        </td>
        <td><img src="https://sbme-tutorials.github.io/2020/data-structure-FALL/images/Tree08.png" alt="inorder"/></td>
        </tr>
        </table>
    </tab>
</tabs>
</td>
</tr>
</table>

## Complexity

<tabs>
<tab title="Test yourself">
<table>
<tr><td></td><td>Worst-case</td><td>Average-case</td><td>Best-case</td></tr>
<tr><td><i>search</i></td><td><i></i></td><td><i></i></td><td><i></i></td></tr>
<tr><td><i>insert</i></td><td><i></i></td><td><i></i></td><td><i></i></td></tr>
<tr><td><i>remove</i></td><td><i></i></td><td><i></i></td><td><i></i></td></tr>
</table>
</tab>
<tab title="Validate">
<table>
<tr><td></td><td>Worst-case</td><td>Average-case</td><td>Best-case</td></tr>
<tr><td><i>search</i></td><td><i>O(n)</i></td><td><i>O(log n)</i></td><td><i>O(1)</i></td></tr>
<tr><td><i>insert</i></td><td><i>O(n)</i></td><td><i>O(log n)</i></td><td><i>O(1)</i></td></tr>
<tr><td><i>remove</i></td><td><i>O(n)</i></td><td><i>O(log n)</i></td><td><i>O(log n)</i></td></tr>
</table>
</tab>
</tabs>


