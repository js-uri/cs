# Priority Queue

<video src="https://youtu.be/wptevk0bshY" preview-src="pq.jpeg" mini-player="true" width="900" />

## Definition

<table>
<tr>
<td>

![queue2.jpeg](queue2.jpeg)
{ thumbnail="true"}

</td>
<td>

![pq.jpeg](pq.jpeg)
{ thumbnail="true"}

</td>
</tr>
</table>


<note>
A priority queue is a special type of queue in which each element is associated with a priority and is served according to its priority. If elements with the same priority occur, they are served according to their order in the queue.
</note>

### Applications

<table>
<tr>
<td>

**Data compression in Huffman code**

<br/>

![pq1.jpeg](pq1.jpeg)
{ thumbnail="true"}

</td>
<td>

**Network Routing**

<br/>

![pq2.jpeg](pq2.jpeg)
{ thumbnail="true"}

</td>
<td>

**CPU Scheduling**

<br/>

![pq3.jpeg](pq3.jpeg)
{ thumbnail="true"}

</td>
</tr>
<tr>
<td colspan="3">

**Other Examples**

- Dijkstra's algorithm
- Prim's algorithm
- Huffman coding
- Discrete event simulation
- Operating systems
- Artificial intelligence
- Data compression
- Data encryption
- Event-driven simulation such as customers waiting in a queue.
- Finding Kth largest/smallest element.
- Scheduling tasks based on priority.

</td>
</tr>
</table>

### Properties

<procedure>

<table>
<tr>
<td>

**Reflexive**

<br/>

```tex
k_1 \le k_2
```

</td>
<td>

**Antisymmetric**

<br/>

```tex
\begin{align*}
k_1 \le k_2 \land k_2 \le k_1  \\ \\
\Rightarrow k_1 = k_2
\end{align*}
```

</td>
<td>

**Transitive**

<br/>

```tex
\begin{align*}
k_1 \le k_2 \land k_2 \le k_3  \\ \\
\Rightarrow k_1 \le k_3
\end{align*}
```

</td>
</tr>
</table>

<table>
<tr>
<td>

**Queue**

- basic operations: 
  - enqueue, dequeue, front, rear, isEmpty, isFull, size, clear, display
- always remove the item least recently added

</td>
<td>

**Priority Queue**

- basic operations: 
  - insert, removeMax, getMax, isEmpty, isFull, size, clear, display
- MaxPQ
  - always remove the item with the highest priority
- MinPQ
  - always remove the item with the lowest priority

</td>
</tr>
</table>

</procedure>

![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Priority-Queue-min-1024x512.png)

### Operations and Implementation

<procedure>

<deflist collapsible="true" default-state="collapsed">

<def title="Enqueue">

Adds an item to the queue based on priority.

```text
procedure enqueue(item, priority)
    if queue is full
        return overflow error
    else
        insert item at the rear of the queue
        insert priority at the rear of the queue
end procedure
```

</def>
<def title="Dequeue">

Removes an item from the queue based on priority.

```text
procedure dequeue()
    if queue is empty
        return underflow error
    else
        remove item from the front of the queue
        remove priority from the front of the queue
end procedure
```

</def>
<def title="Front">

Get the highest priority item from the queue.

```text
procedure front()
    if queue is empty
        return underflow error
    else
        return item at the front of the queue
end procedure
```

</def>
<def title="Rear">

Get the lowest priority item from the queue.

```text
procedure rear()
    if queue is empty
        return underflow error
    else
        return item at the rear of the queue
end procedure
```

</def>
<def title="isEmpty">

Check if the queue is empty.

```text
procedure isEmpty()
    if queue is empty
        return true
    else
        return false
end procedure
```

</def>
<def title="isFull">

Check if the queue is full.

```text
procedure isFull()
    if queue is full
        return true
    else
        return false
end procedure
```

</def>
<def title="Size">

Get the number of items in the queue.

```text
procedure size()
    return number of items in the queue
end procedure
```

</def>
<def title="Clear">

Clear the queue.

```text
procedure clear()
    remove all items from the queue
end procedure
```

</def>
<def title="Display">

Display the items in the queue.

```text
procedure display()
    for each item in the queue
        print item
end procedure
```

</def>
<def title="Change Priority">

Change the priority of an item in the queue.

```text
procedure changePriority(item, priority)
    if queue is empty
        return underflow error
    else
        for each item in the queue
            if item = item
                change priority of item to priority
                return
            end if
        end for
        return item not found error
end procedure
```

</def>
<def title="Peek">

Get the priority of an item in the queue.

```text

procedure peek(item)
    if queue is empty
        return underflow error
    else
        for each item in the queue
            if item = item
                return priority of item
            end if
        end for
        return item not found error
end procedure
```

</def>
<def title="Contains">

Check if an item is in the queue.

```text
procedure contains(item)
    if queue is empty
        return false
    else
        for each item in the queue
            if item = item
                return true
            end if
        end for
        return false
end procedure
```

</def>
<def title="Copy">

Copy the queue to another queue.

```text
procedure copy()
    create a new queue
    for each item in the queue
        insert item at the rear of the new queue
    end for
    return new queue
end procedure
```

</def>
<def title="Split">

Split a queue into two queues.

```text 
procedure split()
    create two new queues
    for each item in the queue
        if item is even
            insert item at the rear of the first new queue
        else
            insert item at the rear of the second new queue
        end if
    end for
    return two new queues
end procedure
```

</def>
<def title="Sort">

Sort the items in the queue based on priority.

```text
procedure sort()
    create a new queue
    while queue is not empty
        remove item from the front of the queue
        insert item at the rear of the new queue
    end while
    return new queue
end procedure
```

</def>
<def title="Shuffle">

Shuffle the items in the queue.

```text
procedure shuffle()
    create a new queue
    while queue is not empty
        remove item from the front of the queue
        insert item at a random position in the new queue
    end while
    return new queue
end procedure
```

</def>
<def title="Swap">

Swap two items in the queue.

```text
procedure swap(item1, item2)
    if queue is empty
        return underflow error
    else
        for each item in the queue
            if item = item1
                swap item1 with item2
                return
            end if
        end for
        return item1 not found error
end procedure
```

</def>
</deflist>

</procedure>

### Performance

<table>
<tr>
<th>Operation</th>
<th>Sorted Array/List</th>
<th>Unsorted Array/List</th>
</tr>
<tr>
<td>Insert</td>
<td>

```tex
O(n)
```
</td>
<td>

```tex
O(1)
```
</td>
</tr>
<tr>
<td>Remove</td>
<td>

```tex
O(1)
```
</td>
<td>

```tex
O(n)
```
</td>
</tr>
<tr>
<td>Find Max/Min</td>
<td>

```tex
O(1)
```
</td>
<td>

```tex
O(n)
```
</td>
</tr>

</table>

### Implementations

<table>
<tr>
<th>Collection Type</th>
<th>Insert</th>
<th>Remove</th>
<th>Peek</th>
</tr>
<tr>
<td>Array</td>
<td>

```tex
O(1)
```
</td>
<td>

```tex
O(1)
```
</td>
<td>

```tex
O(1)
```
</td>
</tr>
<tr>
<td>Linked List</td>
<td>

```tex
O(n)
```
</td>
<td>

```tex
O(1)
```
</td>
<td>

```tex
O(1)
```
</td>
</tr>
<tr>
<td>Binary Heap</td>
<td>

```tex
O(log n)
```
</td>
<td>

```tex
O(log n)
```
</td>
<td>

```tex
O(1)
```
</td>
</tr>
<tr>
<td>Binary Search Tree</td>
<td>

```tex
O(log n)
```
</td>
<td>

```tex
O(log n)
```
</td>
<td>

```tex
O(1)
```
</td>
</tr>
</table>

*_Note: Assumes all collections are unsorted_*

### Advantages and Disadvantages

<table>
<tr>
<td>Advantages</td>
<td>Disadvantages</td>
</tr>
<tr>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Faster access">
    Elements in a priority queue are ordered by priority, one can easily retrieve the highest priority element without having to search through the entire queue.
</def>
<def title="Efficient">
    Are used in many algorithms to improve their efficiency, such as Dijkstra’s algorithm for finding the shortest path in a graph and the A* search algorithm for pathfinding.
</def>
<def title="Dynamic Ordering">
    Elements in a priority queue can have their priority values updated, which allows the queue to dynamically reorder itself as priorities change.
</def>
<def title="Real-time systems">
    Allow you to quickly retrieve the highest priority element, they are often used in real-time systems where time is of the essence.
</def>
</deflist>
</td>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Complexity">
    Are more complex than simple data structures like arrays and linked lists, and may be more difficult to implement and maintain.
</def>
<def title="Less efficient">
    In some cases, other data structures like heaps or binary search trees may be more efficient for certain operations, such as finding the minimum or maximum element in the queue.
</def>
<def title="Memory">
    Storing the priority value for each element in a priority queue can take up additional memory, which may be a concern in systems with limited resources.
</def>
<def title="Less predictable">
    The order of elements in a priority queue is determined by their priority values, the order in which elements are retrieved may be less predictable than with other data structures like stacks or queues, which follow a first-in, first-out (FIFO) or last-in, first-out (LIFO) order.
</def>
</deflist>
</td>
</tr>
</table>







