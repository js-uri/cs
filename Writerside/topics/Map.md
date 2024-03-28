# Map & Unordered Map

<video src="https://youtu.be/aEgG4pidcKU" preview-src="map.jpeg" controls="true"/>

## Define

> A map is a collection of key-value pairs where each key is unique. It is also known as an associative array, dictionary, or hash table. 

> An unordered map is a map that does not maintain the order of the elements.

## Use Cases 

<table>
<tr>
<td colspan="4">Map</td>
</tr>
<tr>
<td>

**Databases**

![](https://www.ionos.com/digitalguide/fileadmin/DigitalGuide/Teaser/object-storage-t.jpg)

Maps are used in database indexing to swiftly retrieve records based on unique keys, such as primary keys.

</td>
<td>

**Caching**

![](https://i.ytimg.com/vi/qsG7PsiEOcg/maxresdefault.jpg)

Maps are used in caching mechanisms to quickly access cached data. Keys typically represent URLs, file paths, or query results.

</td>
<td>

**Symbol Tables**

![](https://3.bp.blogspot.com/-BEk7U63kwxo/W72GP7DhO5I/AAAAAAAAF14/cUsEL7AyBuoDNUdSf3h_NbvCYUr4xe6AQCLcBGAs/s1600/Symbol%2BTable%2B%25281%2529.png)

Compilers and interpreters employ maps to store identifiers (e.g., variable names) and associated attributes (e.g., data types).

</td>
<td>

**Network Routing**

![](https://www.tenforums.com/attachments/network-sharing/84486d1485968022t-network-routing-tables-route.png)

In networking, maps are utilized to map destination addresses to routes for efficient packet forwarding.
</td>
</tr>
<tr>
<td colspan="4">Unordered Map</td>
</tr>
<tr>
<td>

**Caching**

![](https://i.ytimg.com/vi/qsG7PsiEOcg/maxresdefault.jpg)

Unordered maps are used in caching mechanisms to quickly access cached data. Keys typically represent URLs, file paths, or query results.

</td>
<td>

**Frequency Counting**

![](https://micvog.files.wordpress.com/2015/06/step_2_lossy_counting.png?w=1364&h=614)

It is helpful in counting the frequency of elements in a dataset, for example, counting word occurrences in a text corpus.

</td>
<td>

**Graph Algorithms**

![](https://raw.githubusercontent.com/kdn251/interviews/master/images/dijkstra.gif)

In graph algorithms like Dijkstra’s algorithm, an unordered_map can be used to track the shortest distance to each vertex.

</td>
<td>

**Configuration Settings**

![](https://lh6.googleusercontent.com/--wg44mQka3c/VC4mkvm1VZI/AAAAAAAAAAs/wWX1a4H9U9U/s1600/Kernel%2BConfiguration.png)

Storing configuration parameters in an unordered_map is common, where keys represent setting names and values store corresponding values.

</td>
</tr>
</table>

### Advantages & Disadvantages

<table>
    <tr>
        <th>Advantages</th>
        <th>Disadvantages</th>
    </tr>
    <tr>
        <td>
            <ul>
                <li>Efficient for key-value pair storage and retrieval</li>
                <li>Provides fast access to data based on keys</li>
                <li>Supports quick lookup operations</li>
                <li>Allows for easy association of data with unique identifiers (keys)</li>
                <li>Facilitates easy sorting and iteration based on keys</li>
                <li>Provides functionalities for insertion, deletion, and search</li>
                <li>Flexible and adaptable to various applications</li>
            </ul>
        </td>
        <td>
            <ul>
                <li>Can be memory-intensive, especially for large datasets</li>
                <li>May have slower insertion and deletion times compared to other data structures, especially in worst-case scenarios</li>
                <li>Requires additional memory overhead for maintaining the internal structure (e.g., tree or hash table)</li>
                <li>Performance may degrade with hash collisions or unbalanced trees</li>
                <li>Not suitable for applications requiring sequential access to data</li>
                <li>May require implementation-specific optimizations for performance-critical applications</li>
            </ul>
        </td>
    </tr>
</table>


## Implementation

<table>
<tr>
<td>

![](https://media.geeksforgeeks.org/wp-content/uploads/20230306161053/mp2.png)
{thumbnail="center"}
</td>
</tr>
<tr>
<td>

**Ordered Map**

<deflist collapsible="true">
<def title="node">

```text
struct Node {
    int key;
    int value;
    Node* next;
    Node* prev;
};
```
</def>
<def title="map">

```text 
MyMap() - Constructor
```
</def>
<def title="insert">

```text
insert(key, value) - Insert key-value pair
    // Recursive helper function
    insertRecursive(node, key, value):
        if node is null:
            return new Node(key, value)
        if key < node.key:
            node.left = insertRecursive(node.left, key, value)
        else if key > node.key:
            node.right = insertRecursive(node.right, key, value)
        else:
            // Key already exists, update value
            node.value = value
        return node
```
</def>
<def title="remove">

```text
remove(key) - Remove key-value pair
    // Recursive helper function
    removeRecursive(node, key):
        if node is null:
            return node
        if key < node.key:
            node.left = removeRecursive(node.left, key)
        else if key > node.key:
            node.right = removeRecursive(node.right, key)
        else:
            if node.left is null:
                temp = node.right
                delete node
                return temp
            else if node.right is null:
                temp = node.left
                delete node
                return temp
            temp = findMin(node.right)
            node.key = temp.key
            node.value = temp.value
            node.right = removeRecursive(node.right, temp.key)
        return node
    root = removeRecursive(root, key)
    count--
```
</def>
<def title="contains">

```text
contains(key) - Check if key exists
    // Recursive helper function
    containsRecursive(node, key):
        if node is null:
            return false
        if key == node.key:
            return true
        else if key < node.key:
            return containsRecursive(node.left, key)
        else:
            return containsRecursive(node.right, key)
    return containsRecursive(root, key)
```
</def>
<def title="size">

```text
size() - Get size of map
    return count
```
</def>
</deflist>
</td>
</tr>
</table>

<table>
<tr>
<td>

![](https://media.geeksforgeeks.org/wp-content/uploads/20230306161718/mp3.png)
{thumbnail="center"}
</td>
</tr>
<tr>
<td>

**Unordered Map**

<deflist collapsible="true">
<def title="hash function">

```text
hash(key) - Hash function
    return key % capacity
```
</def>
<def title="bucket">

```text
struct Bucket {
    int key;
    int value;
    Bucket* next;
};
```
</def>
<def title="map">

```text
MyUnorderedMap() - Constructor
```
</def>
<def title="insert">

```text
insert(key, value) - Insert key-value pair
    index = hash(key)
    if buckets[index] is null:
        buckets[index] = new Bucket(key, value)
    else:
        // Handle collisions with chaining
        Bucket* temp = buckets[index]
        while temp.next is not null:
            temp = temp.next
        temp.next = new Bucket(key, value)
```
</def>
<def title="remove">

```text
remove(key) - Remove key-value pair
    index = hash(key)
    if buckets[index] is null:
        return
    if buckets[index].key == key:
        buckets[index] = buckets[index].next
    else:
        // Find key in chain
        Bucket* prev = buckets[index]
        Bucket* curr = prev.next
        while curr is not null:
            if curr.key == key:
                prev.next = curr.next
                return
            prev = curr
            curr = curr.next
```
</def>
<def title="contains">

```text
contains(key) - Check if key exists
    index = hash(key)
    Bucket* temp = buckets[index]
    while temp is not null:
        if temp.key == key:
            return true
        temp = temp.next
    return false
```
</def>
<def title="size">

```text
size() - Get size of map
    count = 0
    for i = 0 to capacity-1:
        Bucket* temp = buckets[i]
        while temp is not null:
            count++
            temp = temp.next
    return count
```
</def>
</deflist>
</td>
</tr>
</table>


### Time Complexity 

<table>
    <thead>
        <tr>
            <th rowspan="2">Operation</th>
            <th colspan="3">Map</th>
            <th colspan="3">Unordered Map</th>
        </tr>
        <tr>
            <th></th>
            <th>Best Case</th>
            <th>Average Case</th>
            <th>Worst Case</th>
            <th>Best Case</th>
            <th>Average Case</th>
            <th>Worst Case</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Insert</td>
            <td><code-block lang="tex"> O(log\ n)</code-block></td>
            <td><code-block lang="tex"> O(log\ n)</code-block></td>
            <td><code-block lang="tex"> O(n)</code-block></td>
            <td><code-block lang="tex"> O(1)</code-block></td>
            <td><code-block lang="tex"> O(1)</code-block></td>
            <td><code-block lang="tex"> O(n)</code-block></td>
        </tr>
        <tr>
            <td>Remove</td>
            <td><code-block lang="tex"> O(log\ n)</code-block></td>
            <td><code-block lang="tex"> O(log\ n)</code-block></td>
            <td><code-block lang="tex"> O(n)</code-block></td>
            <td><code-block lang="tex"> O(1)</code-block></td>
            <td><code-block lang="tex"> O(1)</code-block></td>
            <td><code-block lang="tex"> O(n)</code-block></td>
        </tr>
        <tr>
            <td>Search (Contains)</td>
            <td><code-block lang="tex"> O(log\ n)</code-block></td>
            <td><code-block lang="tex"> O(log\ n)</code-block></td>
            <td><code-block lang="tex"> O(n)</code-block></td>
            <td><code-block lang="tex"> O(1)</code-block></td>
            <td><code-block lang="tex"> O(1)</code-block></td>
            <td><code-block lang="tex"> O(n)</code-block></td>
        </tr>
        <tr>
            <td>Access (Get Value)</td>
            <td><code-block lang="tex"> O(log\ n)</code-block></td>
            <td><code-block lang="tex"> O(log\ n)</code-block></td>
            <td><code-block lang="tex"> O(n)</code-block></td>
            <td><code-block lang="tex"> O(1)</code-block></td>
            <td><code-block lang="tex"> O(1)</code-block></td>
            <td><code-block lang="tex"> O(n)</code-block></td>
        </tr>
    </tbody>
</table>


## Comparison

<table>
<tr>
<td></td>
<td>Array</td>
<td>Set</td>
<td>Map</td>
</tr>
<tr>
<td>Duplicate values</td>
<td>Allowed</td>
<td>Not allowed</td>
<td>Keys must be unique, but duplicate values are allowed</td>
</tr>
<tr>
<td>Order</td>
<td>Ordered</td>
<td>Unordered</td>
<td>Unordered</td>
</tr>
<tr>
<td>Size</td>
<td>Static</td>
<td>Dynamic</td>
<td>Dynamic</td>
</tr>
<tr>
<td>Retrieval</td>
<td>By index</td>
<td>By value</td>
<td>By key</td>
</tr>
<tr>
<td>Operations</td>
<td>Access, Insert, Delete</td>
<td>Insert, Delete, Find</td>
<td>Insert, Delete, Find</td>
</tr>
<tr>
<td>Memory</td>
<td>Stored as contiguous blocks of memory</td>
<td>Implemented using linked lists or trees</td>
<td>Implemented using linked lists or trees</td>
</tr>
</table>




