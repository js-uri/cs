# Set

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



## Programming

<tabs>
<tab title="Pseudo-implementation">
<code-block lang="plain text">
    Set Data Structure:
    - Initialize an empty data structure to hold unique elements.
    &nbsp;
    Function Insert(value):
    1. Check if the value is already in the set. 
    2. If not, add the value to the set.
    &nbsp;
    Function Contains(value):
    1. Search the set for the value.
    2. Return true if found, false otherwise.
    &nbsp;
    Function Remove(value):
    1. Search the set for the value.
    2. If found, remove the value from the set.
    &nbsp;
    Function Display():
    1. Iterate through the set and display its elements.
</code-block>
</tab>
<tab title="Code-implementation">

<blockquote>We use the <code>std::unordered_set</code> container from the C++ Standard Library, which is a hash 
table-based implementation of a set.<br/>
We insert, check for existence, and remove elements using the insert, find, and erase methods.<br/>
Finally, we display the elements in the set.</blockquote>

```c++
    #include &lt;iostream>
    #include &lt;unordered_set>
    int main() {
        std::unordered_set<int> mySet;
    &nbsp;
        // Insert elements
        mySet.insert(10);
        mySet.insert(5);
        mySet.insert(20);
    &nbsp;
        // Check if an element exists
        if (mySet.find(5) != mySet.end()) {
            std::cout << "Element 5 found in the set.\n";
        }
    &nbsp;
        // Remove an element
        mySet.erase(10);
    &nbsp;
        // Display the elements
        std::cout << "Set elements: ";
        for (const int& element : mySet) {
            std::cout << element << " ";
        }
        std::cout << "\n";
        return 0;
    }
```

```text
Element 5 found in the set.
5 20
```

</tab>
</tabs>



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