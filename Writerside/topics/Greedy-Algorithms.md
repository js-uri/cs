---
switcher-label: Language
---

# Greedy Algorithms

<video src="https://youtu.be/bC7o8P_Ste4?feature=shared" preview-src="ga.jpeg" width="900" />


## Defined

> Greedy algorithms are algorithms that make the locally optimal choice at each step with the hope of finding a global optimum. Greedy algorithms are used in optimization problems where the goal is to find the best solution from a set of possible solutions. The greedy algorithm makes a series of choices that are locally optimal, but may not be globally optimal.

{ style="note" }

## Greedy Choice Property

<procedure>

A greedy algorithm must have two properties:

<deflist collapsible="true">
    <def title="Greedy Choice Property">
        This is the key principle that defines greedy algorithms. It states that at each step of the algorithm, the best possible choice is made without considering the consequences of that choice beyond the current step. This is what makes greedy algorithms "shortsighted" as they focus solely on immediate gain.
    </def>
    <def title="Optimal Substructure">
        Many problems have optimal substructure, which means that an optimal solution to the problem can be constructed from optimal solutions to its subproblems. Greedy algorithms exploit this property to efficiently find the global optimum.
    </def>
</deflist>

This means that the greedy algorithm makes the best choice at each step, without considering the larger problem. The greedy algorithm continues to make these choices until a solution is found.
</procedure>

## Properties

<procedure>

<deflist style="full" collapsible="false">
    <def title="Efficiency">
        Greedy algorithms are generally efficient and easy to implement. They are often used to solve optimization problems where the goal is to find the best solution from a set of possible solutions.
    </def>
    <def title="Optimality">
        Greedy algorithms do not always produce the optimal solution, but they often produce solutions that are close to the optimal solution. The greedy algorithm makes the best choice at each step, hoping to find the global optimum.
    </def>
    <def title="Applications">
        Greedy algorithms are used in a wide range of applications, including network design, data compression, and scheduling tasks. They are particularly useful in problems where the optimal solution can be constructed from optimal solutions to subproblems.
    </def>
</deflist>
</procedure>


## Advantages & Disadvantages

<table>
<tr>
<td>✅</td>
<td>❌</td>
</tr>
<tr>
<td>Easy to implement</td>
<td>May not always produce the optimal solution</td>
</tr>
<tr>
<td>Efficient for many problems</td>
<td>Can be difficult to prove correctness</td>
</tr>
<tr>
<td>Useful for problems with optimal substructure</td>
<td>May require additional work to ensure correctness</td>
</tr>
</table>


## Applications

<table>
<tr>
<td>

**Network Design**

<br/>

![](https://d2slcw3kip6qmk.cloudfront.net/marketing/blog/2019Q2/network-infrastructure-mapping/cisco-network-diagram.png)
{ thumbnail="true" width="900" }

<br/>

In network design, such as in laying out cables or pipes, the Kruskal's or Prim's algorithm can be used to find the minimum spanning tree, minimizing the total cost.

</td>
<td>

**Data Compression**

<br/>

![](http://www.convexapp.com/wp-content/uploads/2019/12/data-compression-model.png)
{ thumbnail="true" width="900" }

<br/>

In data compression, Huffman coding is a greedy algorithm used to construct variable-length codes for efficient data compression.

</td>
<td>

**Scheduling Tasks**

<br/>

![](https://blogs.sw.siemens.com/wp-content/uploads/sites/51/2018/05/priority.png)
{ thumbnail="true" width="900" }

<br/>

Scheduling tasks to maximize productivity. For example, a project manager can use a greedy algorithm to select activities with the earliest end times.
</td>
</tr>
</table>


## Complexity

<procedure>

The time complexity of a greedy algorithm depends on the specific problem being solved. In general, greedy algorithms have a time complexity of `O(n log n)` or `O(n)`, where n is the size of the input. The space complexity of a greedy algorithm is typically `O(1)` or `O(n)`, depending on the problem.

</procedure>


## Examples

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


### Coin Change Problem

The coin change problem is another classic optimization problem that can be solved using a greedy algorithm. The problem is defined as follows:

> Given a set of coins with different denominations, find the minimum number of coins needed to make a certain amount of change.


#### Example 1

<table>
<tr>
<td>

**Input**

A set of coin denominations, represented as an array or list of integers.
A target amount of money to make up using these coins.
</td>
<td>

**Output**

The minimum number of coins required to make up the target amount.
</td>
</tr>
<tr>
<td colspan="2">

> **Example**  
Coins: [1, 5, 10, 25]  
Target amount: 30  
Solution: 2 (using one 25-cent coin and one 5-cent coin)
</td>
</tr>
<tr>
<td colspan="2">

The greedy algorithm for the coin change problem works as follows:

1. Sort the coins in descending order based on their denominations.
2. Initialize a variable to keep track of the number of coins used.
3. Iterate through the sorted denominations:  
   i. At each step, if the current denomination is less than or equal to the remaining amount, subtract that denomination from the remaining amount and increment the coin count.  
   ii. Repeat this process until the remaining amount becomes zero.
</td>
</tr>
</table>


#### Example 2

<table>
<tr>
<td>

**Input**

A set of coin denominations, represented as an array or list of integers.
A target amount of money to make up using these coins.
</td>
<td>

**Output**

The minimum number of coins required to make up the target amount.
</td>
</tr>
<tr>
<td colspan="2">

>
> Coins: [1, 3, 4, 5]  
Target amount: 7  
Solution: ???
</td>
</tr>
<tr>
<td colspan="2">

<deflist collapsible="true">
<def title="Solution">

Solution (we get)  : 3 (using one 5-cent coin and two 1-cent coins)  
Solution (we want) : 2 (using one 3-cent coin and one 4-cent coin)

The solution does not adhere to the greedy algorithm. The greedy algorithm would choose the 5-cent coin first, followed by the 1-cent coin, resulting in a total of 3 coins.
</def>
</deflist>

</td>
</tr>
</table>








