# Breadth-first

<video src="https://youtu.be/HZ5YTanv5QE" preview-src="bfs_video.jpeg" width="900" controls="true"/>

> Breadth-first search (BFS) is an algorithm for traversing or searching tree or graph data structures. It starts at the tree root (or some arbitrary node of a graph, sometimes referred to as a 'search key') and explores the neighbor nodes first, before moving to the next level neighbors.

{ style="note" }

<procedure>

<tabs>
<tab title="Shortest Paths">

> **Problem**
> 
> Find directed path from `s` to each other vertex that uses the fewest edges

<br/>

> **Key Idea**
> 
> Visit vertices in increasing order of distance from `s`


> Try writing some of the paths from 0 -> 6  
> 
> 0 - 2 - 7 - 4 - 5 - 1 - 3 - 6

![](bfs_shortest_path.jpeg)
{ thumbnail="true" width="900"}

<br/>

<deflist collapsible="true">
<def title="possible directed paths from 0 -> 6">

0 -> 2 -> 7 -> 4 -> 5 -> 1 -> 3 -> 6  
0 -> 2 -> 7 -> 5 -> 1 -> 3 -> 6  
0 -> 4 -> 5 -> 1 -> 3 -> 6  
**0 -> 2 -> 7 -> 3 -> 6**

</def>
</deflist>

<br/>

> **Key Structure**
> 
> a queue to store vertices to visit

<br/>

![](bfs_breadth.jpeg)
{ thumbnail="true" width="900" }

</tab>
<tab title="BFS">

> **Repeat until queue is empty**
> 
> Remove vertex `v` from queue
> Add to queue all unmarked vertices adjacent from `v` and mark them

<br/>

![](bfs.png)
{ thumbnail="true" width="900" }

<br/>

```text
queue = new Queue()
queue.enqueue(s)
while queue is not empty
    v = queue.dequeue()
    for each unmarked vertex w adjacent to v
        queue.enqueue(w)
        mark w
```

<br/>

<table>
<tr>
<td>

![](bfs_x2.jpeg)
{ thumbnail="true" width="900" }
</td>
<td>

![](bfs_x1.jpeg)
{ thumbnail="true" width="900" }

<deflist collapsible="true">
<def title="outcome">

![](bfs_x3.jpeg)
{ thumbnail="true" width="900" }
</def>
</deflist>
</td>
<td>

<table>
<tr>
<td>
v
</td>
<td>
edgeTo[]
</td>
<td>
marked[]
</td>
<td>
distTo[]
</td>
</tr>
<tr>
<td>
0
</td>
<td>
- 
</td>
<td>
true
</td>
<td>
0
</td>
</tr>
<tr>
<td>
1
</td>
<td>
0
</td>
<td>
true
</td>
<td>
1
</td>
</tr>
<tr>
<td>
2
</td>
<td>
0
</td>   
<td>
true
</td>
<td>
1
</td>
</tr>
<tr>
<td>
4 
</td>
<td>
2
</td>
<td>
true
</td>
<td>
2
</td>
</tr>
<tr>
<td>
3
</td>
<td>
4
</td>
<td>
true
</td>
<td>
3
</td>
</tr>
<tr>
<td>
5
</td>
<td>
3
</td>
<td>
true
</td>
<td>
4
</td>
</tr>
</table>
</td>
</tr>
</table>
</tab>
<tab title="Properties">

> **Proposition**
> 
> In the worst case, BFS takes Theta(`E + V`) time 

> **Proof**
> 
> Each vertex and edge is visited once

<br/>

<table>
<tr>
<td>

![](bfs_x4.jpeg)
{ thumbnail="true" width="900" }
</td>
<td>

![](bfs_x5.jpeg)
{ thumbnail="true" width="900" }
</td>
</tr>
</table>
</tab>
<tab title="Ex1">

> **Single-link Shortest Path**
> 
> Given a digraph and a target vertex `t`, find shortest path from `s` to `t`

<br/>

<table>
<tr>
<td>

> `t = 0`

<br/>

<deflist collapsible="true">
<def title="Shortest path from 7">
7 -> 6 -> 0
</def>
<def title="Shortest path from 5">
5 -> 4 -> 2 -> 0
</def>
<def title="Shortest path from 12">
12 -> 9 -> 11 -> 4 -> 2 -> 0
</def>
</deflist>
</td>
<td>

![](bfs_x6.jpeg)
{ thumbnail="true" width="900" }
</td>
</tr>
</table>
</tab>
<tab title="Ex2">

> **Multiple-source Shortest Path**
>
> Given a digraph and a set of source vertices, find shortest path from *_any_* vertex in the set to every other vertex

<br/>

<table>
<tr>
<td>

> `S = {1, 7, 10}`

<br/>

<deflist collapsible="true">
<def title="Shortest path to 4">

1 -> no path  
10 -> 12 -> 9 -> 11 -> 4  
**7 -> 6 -> 0**  
</def>
<def title="Shortest path to 5">

1 -> no path  
10 -> 12 -> 9 -> 11 -> 4 -> 3 -> 5  
**7 -> 9 -> 11 -> 4 -> 3 -> 5**  
</def>
<def title="Shortest path to 12">

1 -> no path  
7 -> 9 -> 10/11 -> 12  
**10 -> 12**  
</def>
</deflist>
</td>
<td>

![](bfs_x6.jpeg)
{ thumbnail="true" width="900" }
</td>
</tr>
</table>
</tab>

</tabs>
</procedure>

## Application

<table>
<tr>
<td>

> Fewest number of hops in a communication network

<br/>

![](bfs_x7.jpeg)
{ thumbnail="true" width="900" }

ARPANET, 1969 - 1977
</td>
<td>

> **Problem**
> 
> Find path between `s` and each other vertex that uses fewest edges

<br/>

> **Solution**
> 
> Treat as a digraph, replacing each undirected edge with two anti-parallel edges
{ style="note" }

</td>
</tr>
</table>

## Summary

**BFS and DFS enables efficient solution to many (but not all) graph and digraph problems**

<table>
<tr>
<td>graph problem</td>
<td>BFS</td>
<td>DFS</td>
<td>Complexity</td>
</tr>
<tr>
<td>s-t path</td>
<td>✔︎</td>
<td>✔︎</td>
<td>

```tex
\Theta(E + V)
```
</td>
</tr>
<tr>
<td>shortest s-t path</td>
<td>✔︎</td>
<td></td>
<td>

```tex
\Theta(E + V)
```
</td>
</tr>
<tr>
<td>s-t directed cycle</td>
<td>✔︎</td>
<td></td>
<td>

```tex
\Theta(E + V)
```
</td>
</tr>
<tr>
<td>Euler cycle</td>
<td></td>
<td>✔︎</td>
<td>

```tex
\Theta(E + V)
```
</td>
</tr>
<tr>
<td>bipartieness</td>
<td>✔︎</td>
<td>✔︎</td>
<td>

```tex
\Theta(E + V)
```
</td>
</tr>
<tr>
<td>connected components</td>
<td>✔︎</td>
<td>✔︎</td>
<td>

```tex
\Theta(E + V)
```
</td>
</tr>
<tr>
<td>strong components</td>
<td></td>
<td>✔︎</td>
<td>

```tex
\Theta(E + V)
```
</td>
</tr>
<tr>
<td>planarity</td>
<td></td>
<td>✔︎</td>
<td>

```tex
\Theta(E + V)
```
</td>
</tr>
</table>
