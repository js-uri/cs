---
switcher-label: Language
---

# Greedy Algorithms

![greedy algorithms](https://i.ytimg.com/vi/bC7o8P_Ste4/maxresdefault.jpg){width="100%"}

## Python {switcher-key="Python"}

The content that should appear when the Section Once is selected.

## Cpp {switcher-key="Cpp"}

The content that should appear when the Section Two is selected.

## Python2 {switcher-key="Python"}

The content that should appear when the Section Once is selected.



## Definition

Greedy algorithms are a class of algorithms that make a series of choices to arrive at an optimal solution. In each step of the algorithm, a decision is made by selecting the best option available at that moment, without considering the global context. This choice is typically based on a locally optimal criterion. The greedy algorithm continues making these choices until a solution is found.



## Use Cases

<deflist style="full" sorted="asc" collapsible="true">
    <def title="Minimum Spanning Tree">
        In network design, such as in laying out cables or pipes, the Kruskal's or Prim's algorithm can be used to find the minimum spanning tree, minimizing the total cost.
        <br/>
        <a href="https://www.geeksforgeeks.org/what-is-minimum-spanning-tree-mst/">What is Minimum Spanning Tree (MST)</a>
    </def>
    <def title="Huffman Coding">
        In data compression, Huffman coding is a greedy algorithm used to construct variable-length codes for efficient data compression.
        <br/>
        <a href="https://www.geeksforgeeks.org/huffman-coding-greedy-algo-3/">Huffman Coding | Greedy Algo-3</a>
        <a href="https://www.geeksforgeeks.org/huffman-decoding/?ref=lbp">Huffman Decoding</a>
    </def>
    <def title="Activity Selection">
        Scheduling tasks to maximize productivity. For example, a project manager can use a greedy algorithm to select activities with the earliest end times.
        <br/>
        <a href="https://www.geeksforgeeks.org/job-sequencing-problem/?ref=lbp">Job Sequencing Problem</a>
    </def>
    <def title="Dijkstra's Algorithm">
        Used for finding the shortest path in a graph, such as in GPS navigation systems.
        <br/>
        <a href="https://www.geeksforgeeks.org/introduction-to-dijkstras-shortest-path-algorithm/">What is Dijkstra’s Algorithm? | Introduction to Dijkstra’s Shortest Path Algorithm</a>
    </def>
</deflist>



## Pseudocode (General)

```
Greedy Algorithm(Input):
    Initialize an empty solution
    While the solution is not complete:
        Select the best available option
        Add the selected option to the solution
    Return the solution
```

[//]: # (```)

[//]: # (1. Create a priority queue &#40;min-heap&#41; of nodes to store characters and their frequencies.)

[//]: # (2. For each unique character in the input, create a node containing the character and its frequency.)

[//]: # (3. Insert each node into the priority queue.)

[//]: # (4. While there is more than one node in the queue:)

[//]: # (   a. Remove the two nodes with the lowest frequencies from the queue.)

[//]: # (   b. Create a new internal node with a frequency equal to the sum of the two nodes' frequencies.)

[//]: # (   c. Set the two nodes as children of the new internal node.)

[//]: # (   d. Insert the new internal node into the queue.)

[//]: # (5. The remaining node in the queue is the root of the Huffman tree.)

[//]: # (6. Traverse the Huffman tree to assign binary codes to characters.)

[//]: # (7. The binary codes represent the Huffman encoding.)

[//]: # (```)



## Advantages & Disadvantages

<table>
    <tr>
        <td>Advantages</td><td>Disadvantages</td>
    </tr>
    <tr>
        <td>They are relatively easy to understand and implement.<br/>
Greedy algorithms often provide fast solutions.<br/>
They are suitable for solving optimization problems with certain conditions.</td><td>They may not always guarantee the optimal solution. Greedy choices made in earlier steps can lead to suboptimal results.<br/>
Determining whether a problem can be solved optimally using a greedy approach can be challenging.</td>
    </tr>
</table>



[//]: # (<table>)

[//]: # (    <tr>)

[//]: # (        <td>Minimum Spanning Tree</td><td>Huffman Coding</td>)

[//]: # (    </tr>)

[//]: # (    <tr>)

[//]: # (        <td>In network design, such as in laying out cables or pipes, the Kruskal's or Prim's algorithm can be used to find the minimum spanning tree, minimizing the total cost.</td><td>In data compression, Huffman coding is a greedy algorithm used to construct variable-length codes for efficient data compression.</td>)

[//]: # (    </tr>)

[//]: # (</table>)

[//]: # ()
[//]: # (<table>)

[//]: # (    <tr>)

[//]: # (        <td>Activity Selection</td><td>Dijkstra's Algorithm</td>)

[//]: # (    </tr>)

[//]: # (    <tr>)

[//]: # (        <td>Scheduling tasks to maximize productivity. For example, a project manager can use a greedy algorithm to select activities with the earliest end times.</td><td>Used for finding the shortest path in a graph, such as in GPS navigation systems.</td>)

[//]: # (    </tr>)

[//]: # (</table>)

