# Set & Unordered Set

<video src="https://youtu.be/SvvvGT3qD1Y?feature=shared" preview-src="set_image.png"/>



## Overview



### Definition

> A set is a fundamental data structure in computer science that stores a collection of unique elements. It ensures that no duplicates are allowed, and it doesn't impose a specific order on the elements.



### Use Cases

<table>
<tr>
<td>
<p>Database Indexing</p><br/>
<img src="https://cdn-media-1.freecodecamp.org/images/0eg06hWYJWhXPt1QNuaDlETYrmnSKAo6Nf44" alt=""/><br/>
<p>Sets are used to maintain unique values in database indexes, ensuring fast lookups.</p>
</td>
<td>
<p>Spell Checking</p><br/>
<img src="https://www.seas.upenn.edu/~cis120/archive/16sp/hw/hw08/diagram.png" alt="alt"/><br/>
<p>In word processing applications, a `set` can be used to maintain a dictionary of correctly spelled words.</p>
</td>
<td>
<p>Graph Algorithms</p><br/>
<img src="https://raw.githubusercontent.com/kdn251/interviews/master/images/dijkstra.gif" alt=""/><br/>
<p>Sets can be used to track visited nodes in graph traversal algorithms.</p>
</td>
<td>
<p>Membership Testing</p><br/>
<img src="https://www.researchgate.net/profile/Vassilios-Vassilakis/publication/318440316/figure/fig3/AS
:608741581934592@1522146711030/Illustrating-the-false-positives-during-a-membership-test.png" alt=""/><br/>
<p>Sets are efficient for checking whether an element is part of a specific group or category.</p>
</td>
</tr>
</table>



### Advantages & Disadvantages

<table>
    <tr>
    <td>✅</td><td>❌</td>
    </tr>
    <tr>
    <td>
    <deflist collapsible="true">
        <def title="Uniqueness" collapsible="true" default-state="collapsed">
        Sets enforce uniqueness, ensuring no duplicate elements.
        </def>
    <def title="Fast Lookup" collapsible="true" default-state="collapsed">
    Efficient for searching and checking if an element exists.
    </def>
        <def title="Simple Interface" collapsible="true" default-state="collapsed">
        Typically provides simple and intuitive methods like `insert`, `contains`, and `remove`.
        </def>
    </deflist>
    </td>
    <td>
    <deflist collapsible="true">
        <def title="No Ordering" collapsible="true" default-state="collapsed">
        Elements are not stored in a specific order, which may be a disadvantage in some use cases.
        </def>
        <def title="Overhead" collapsible="true" default-state="collapsed">
        May require more memory and have some overhead for maintaining uniqueness.
        </def>
        <def title="Slower Insertions" collapsible="true" default-state="collapsed">
        Inserting elements can be slower compared to data structures optimized for insertion.
        </def>
    </deflist>
    </td>
    </tr>
</table>



## Implementation

<table>
<tr>
<td colspan="4">

![](https://media.geeksforgeeks.org/wp-content/uploads/20230302151935/s.png)


</td>
</tr>
<tr>
<td>

**Set**

*_balanced binary search tree implementation_*

<deflist collapsible="true">
<def title="insert">

Adds an element to the set if it doesn't already exist.

```text
insert(node, data):
    if node is null:
        return new Node(data)
    if data < node.data:
        node.left = insert(node.left, data)
    else if data > node.data:
        node.right = insert(node.right, data)
    return node
```
</def>
<def title="remove">

Deletes an element from the set.

```text
remove(node, data):
    if node is null:
        return node
    if data < node.data:
        node.left = remove(node.left, data)
    else if data > node.data:
        node.right = remove(node.right, data)
    else:
        if node.left is null:
            return node.right
        else if node.right is null:
            return node.left
        node.data = minValue(node.right)
        node.right = remove(node.right, node.data)
    return node
```
</def>
<def title="contains">

Checks if an element is present in the set.

```text
contains(node, data):
    if node is null:
        return false
    if data < node.data:
        return contains(node.left, data)
    else if data > node.data:
        return contains(node.right, data)
    return true
```
</def>
<def title="minValue">

Finds the minimum value in a subtree.

```text
minValue(node):
    current = node
    while current.left is not null:
        current = current.left
    return current.data
```
</def>
<def title="size">

Returns the number of elements in the set.

```text
size(node):
    if node is null:
        return 0
    return 1 + size(node.left) + size(node.right)
```
</def>
<def title="minValue">

Finds the minimum value in a subtree.

```text
minValue(node):
    current = node
    while current.left is not null:
        current = current.left
    return current.data
```
</def>
<def title="maxValue">

Finds the maximum value in a subtree.

```text
maxValue(node):
    current = node
    while current.right is not null:
        current = current.right
    return current.data
```
</def>
</deflist>
</td>
</tr>
<tr>
<td>

**Unordered set**

*_hash table implementation_*

<deflist collapsible="true">
<def title="hash">

Maps elements to unique indices in the hash table.

```text
hash(data):
    return data % tableSize
```
</def>
<def title="insert">

Adds an element to the set.

```text
insert(data):
    index = hash(data)
    for item in buckets[index]:
        if item equals data:
            return // Element already exists
    add data to buckets[index]
```
</def>
<def title="remove">

Deletes an element from the set.

```text
remove(data):
    index = hash(data)
    for item in buckets[index]:
        if item equals data:
            remove item from buckets[index]
            return
```
</def>
<def title="contains">

Checks if an element is present in the set.

```text
contains(data):
    index = hash(data)
    for item in buckets[index]:
        if item equals data:
            return true
    return false
```
</def>
<def title="size">

Returns the number of elements in the set.

```text
size():
    count = 0
    for bucket in buckets:
        count += bucket.size()
    return count
```
</def>
<def title="min">

Finds the minimum value in the set.

```text
min():
    minVal = INT_MAX
    for bucket in buckets:
        for item in bucket:
            minVal = min(minVal, item)
    return minVal
```
</def>
<def title="max">

Finds the maximum value in the set.

```text
max():
    maxVal = INT_MIN
    for bucket in buckets:
        for item in bucket:
            maxVal = max(maxVal, item)
    return maxVal
```
</def>
</deflist>
</td>
</tr>
</table>


### Time Complexity

<table>
    <tr>
        <th>Data Structure</th>
        <th>Operation</th>
        <th>Best Case</th>
        <th>Average Case</th>
        <th>Worst Case</th>
    </tr>
    <tr>
        <td rowspan="4">Set (Binary Search Tree)</td>
        <td>Insert</td>
        <td><code-block lang="tex"> O(log\ n)</code-block></td>
        <td><code-block lang="tex"> O(log\ n)</code-block></td>
        <td><code-block lang="tex"> O(n)</code-block></td>
    </tr>
    <tr>
        <td>Delete</td>
        <td><code-block lang="tex"> O(log\ n)</code-block></td>
        <td><code-block lang="tex"> O(log\ n)</code-block></td>
        <td><code-block lang="tex"> O(n)</code-block></td>
    </tr>
    <tr>
        <td>Search</td>
        <td><code-block lang="tex"> O(log\ n)</code-block></td>
        <td><code-block lang="tex"> O(log\ n)</code-block></td>
        <td><code-block lang="tex"> O(n)</code-block></td>
    </tr>
    <tr>
        <td>Sizeof / Min / Max</td>
        <td><code-block lang="tex"> O(n)</code-block></td>
        <td><code-block lang="tex"> O(n)</code-block></td>
        <td><code-block lang="tex"> O(n)</code-block></td>
    </tr>
    <tr>
        <td rowspan="4">Unordered Set (Hash Table)</td>
        <td>Insert</td>
        <td><code-block lang="tex"> O(1)</code-block></td>
        <td><code-block lang="tex"> O(1)</code-block></td>
        <td><code-block lang="tex"> O(n)</code-block></td>
    </tr>
    <tr>
        <td>Delete</td>
        <td><code-block lang="tex"> O(1)</code-block></td>
        <td><code-block lang="tex"> O(1)</code-block></td>
        <td><code-block lang="tex"> O(n)</code-block></td>
    </tr>
    <tr>
        <td>Search</td>
        <td><code-block lang="tex"> O(1)</code-block></td>
        <td><code-block lang="tex"> O(1)</code-block></td>
        <td><code-block lang="tex"> O(n)</code-block></td>
    </tr>
    <tr>
        <td>Sizeof / Min / Max</td>
        <td><code-block lang="tex"> O(n)</code-block></td>
        <td><code-block lang="tex"> O(n)</code-block></td>
        <td><code-block lang="tex"> O(n)</code-block></td>
    </tr>
</table>

[//]: # (<tabs>)

[//]: # (<tab title="Pseudo-implementation">)

[//]: # (<code-block lang="plain text">)

[//]: # (    Set Data Structure:)

[//]: # (    - Initialize an empty data BST structure to hold unique elements.)

[//]: # (    &nbsp;)

[//]: # (    Function Insert&#40;value&#41;:)

[//]: # (    1. Check if the value is already in the set. )

[//]: # (    2. If not, add the value to the set.)

[//]: # (    &nbsp;)

[//]: # (    Function Contains&#40;value&#41;:)

[//]: # (    1. Search the set for the value.)

[//]: # (    2. Return true if found, false otherwise.)

[//]: # (    &nbsp;)

[//]: # (    Function Remove&#40;value&#41;:)

[//]: # (    1. Search the set for the value.)

[//]: # (    2. If found, remove the value from the set.)

[//]: # (    &nbsp;)

[//]: # (    Function Display&#40;&#41;:)

[//]: # (    1. Iterate through the set and display its elements.)

[//]: # (</code-block>)

[//]: # (</tab>)

[//]: # (<tab title="Code-implementation">)

[//]: # ()
[//]: # (<blockquote>We use the <code>std::unordered_set</code> container from the C++ Standard Library, which is a hash )

[//]: # (table-based implementation of a set.<br/>)

[//]: # (We insert, check for existence, and remove elements using the insert, find, and erase methods.<br/>)

[//]: # (Finally, we display the elements in the set.</blockquote>)

[//]: # ()
[//]: # (```c++)

[//]: # (    #include &lt;iostream>)

[//]: # (    #include &lt;unordered_set>)

[//]: # (    int main&#40;&#41; {)

[//]: # (        std::unordered_set<int> mySet;)

[//]: # (    &nbsp;)

[//]: # (        // Insert elements)

[//]: # (        mySet.insert&#40;10&#41;;)

[//]: # (        mySet.insert&#40;5&#41;;)

[//]: # (        mySet.insert&#40;20&#41;;)

[//]: # (    &nbsp;)

[//]: # (        // Check if an element exists)

[//]: # (        if &#40;mySet.find&#40;5&#41; != mySet.end&#40;&#41;&#41; {)

[//]: # (            std::cout << "Element 5 found in the set.\n";)

[//]: # (        })

[//]: # (    &nbsp;)

[//]: # (        // Remove an element)

[//]: # (        mySet.erase&#40;10&#41;;)

[//]: # (    &nbsp;)

[//]: # (        // Display the elements)

[//]: # (        std::cout << "Set elements: ";)

[//]: # (        for &#40;const int& element : mySet&#41; {)

[//]: # (            std::cout << element << " ";)

[//]: # (        })

[//]: # (        std::cout << "\n";)

[//]: # (        return 0;)

[//]: # (    })

[//]: # (```)

[//]: # ()
[//]: # (```text)

[//]: # (Element 5 found in the set.)

[//]: # (5 20)

[//]: # (```)

[//]: # ()
[//]: # (</tab>)

[//]: # (</tabs>)



[//]: # ()
[//]: # (### Average-Time Complexity)

[//]: # ()
[//]: # ()
[//]: # (`````````` {div} full-width)

[//]: # ()
[//]: # ()
[//]: # (`````````  {card})

[//]: # ()
[//]: # (The time complexity of fundamental operations in a set data structure depends on the specific implementation. There are typically two common implementations: one based on hash tables and another based on balanced binary search trees. I'll provide an overview of the time complexity for these common operations in each type of implementation...)

[//]: # ()
[//]: # ()
[//]: # (`````` {list-table})

[//]: # ()
[//]: # ()
[//]: # (* - )

[//]: # ()
[//]: # (  - Insertion<br>`insert`)

[//]: # ()
[//]: # (  - Deletion<br>`erase`)

[//]: # ()
[//]: # (  - Search<br>`find` || `contains`)

[//]: # ()
[//]: # (* - Hash Table-Based Set<br>`std::unordered_set`)

[//]: # ()
[//]: # (  - $O&#40;1&#41;$)

[//]: # ()
[//]: # (  - $O&#40;1&#41;$)

[//]: # ()
[//]: # (  - $O&#40;1&#41;$)

[//]: # ()
[//]: # (* - Balanced BST-Based Set<br>`std::set`)

[//]: # ()
[//]: # (  - $O&#40;log\ n&#41;$)

[//]: # ()
[//]: # (  - $O&#40;log\ n&#41;$)

[//]: # ()
[//]: # (  - $O&#40;log\ n&#41;$)

[//]: # ()
[//]: # ()
[//]: # (``````)

[//]: # ()
[//]: # (`````````)

[//]: # ()
[//]: # (``````````)