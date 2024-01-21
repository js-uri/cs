# Priority Queue

## 1. Priority Queue?

A priority queue is a special type of queue in which each element is associated with a priority and is served according to its priority. If elements with the same priority occur, they are served according to their order in the queue.

## 2. Operations on Priority Queue

- **Enqueue:** Adds an item to the queue based on priority.
- **Dequeue:** Removes an item from the queue based on priority.
- **Front:** Get the highest priority item from the queue.
- **Rear:** Get the lowest priority item from the queue.
- **isEmpty:** Check if the queue is empty.
- **isFull:** Check if the queue is full.
- **Size:** Get the number of items in the queue.
- **Clear:** Clear the queue.
- **Display:** Display the items in the queue.
- **Change Priority:** Change the priority of an item in the queue.
- **Peek:** Get the priority of an item in the queue.
- **Contains:** Check if an item is in the queue.
- **Copy:** Copy the queue to another queue.
- **Split:** Split a queue into two queues.
- **Sort:** Sort the items in the queue based on priority.
- **Shuffle:** Shuffle the items in the queue.
- **Swap:** Swap two items in the queue.




## 3. Applications of Priority Queue

- **CPU Scheduling:** Priority queues are used in CPU scheduling algorithms to determine the next job to be executed.
- **Graph Algorithms:** Priority queues are used in graph algorithms such as Dijkstra's algorithm and Prim's algorithm.
- **Huffman Coding:** Priority queues are used in Huffman coding to determine the order in which characters are encoded.
- **Discrete Event Simulation:** Priority queues are used in discrete event simulation to determine the next event to be simulated.
- **Operating Systems:** Priority queues are used in operating systems to determine the next process to be executed.
- **Artificial Intelligence:** Priority queues are used in artificial intelligence to determine the next action to be taken.
- **Data Compression:** Priority queues are used in data compression algorithms such as LZ77 and LZ78.
- **Data Encryption:** Priority queues are used in data encryption algorithms such as RSA and AES.
- **Data Structures:** Priority queues are used in data structures such as heaps and binary search trees.
- **Network Routing:** Priority queues are used in network routing algorithms to determine the next node to be visited.
- **Scheduling:** Priority queues are used in scheduling algorithms to determine the next task to be scheduled.
- **Task Scheduling:** Priority queues are used in task scheduling algorithms to determine the next task to be scheduled.
- **Job Scheduling:** Priority queues are used in job scheduling algorithms to determine the next job to be scheduled.

## 4. Types of Priority Queue

- **Min Priority Queue:** In a min priority queue, the item with the lowest priority is served first.
- **Max Priority Queue:** In a max priority queue, the item with the highest priority is served first.
- **Min-Max Priority Queue:** In a min-max priority queue, the item with the lowest priority is served first, and the item with the highest priority is served last.

## 5. Implementation of Priority Queue

```
procedure enqueue(item, priority)
    if queue is full
        return overflow error
    else
        insert item at the rear of the queue
        insert priority at the rear of the queue
end procedure
```

```
procedure dequeue()
    if queue is empty
        return underflow error
    else
        remove item from the front of the queue
        remove priority from the front of the queue
end procedure
```

```
procedure front()
    if queue is empty
        return underflow error
    else
        return item at the front of the queue
end procedure
```

```
procedure rear()
    if queue is empty
        return underflow error
    else
        return item at the rear of the queue
end procedure
```

```
procedure isEmpty()
    if queue is empty
        return true
    else
        return false
end procedure
```

```
procedure isFull()
    if queue is full
        return true
    else
        return false
end procedure
```

```
procedure size()
    return number of items in the queue
end procedure
```

```
procedure clear()
    remove all items from the queue
end procedure
```

```
procedure display()
    for each item in the queue
        print item
end procedure
```

```
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

```
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

```
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

```
procedure copy()
    create a new queue
    for each item in the queue
        insert item at the rear of the new queue
    end for
    return new queue
end procedure
```

```
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

```
procedure sort()
    create a new queue
    while queue is not empty
        remove item from the front of the queue
        insert item at the rear of the new queue
    end while
    return new queue
end procedure
```

```
procedure shuffle()
    create a new queue
    while queue is not empty
        remove item from the front of the queue
        insert item at a random position in the new queue
    end while
    return new queue
end procedure
```

```
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




 