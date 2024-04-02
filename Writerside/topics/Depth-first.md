# Depth-first

<video src="https://youtu.be/Urx87-NMm6c" preview-src="dfs_video.jpeg" width="900" controls="true" />

> Depth-first search (DFS) is an algorithm for traversing or searching tree or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.
> 
{ style="note" }

<procedure>

<tabs>
<tab title="Reachability">

**Problem**

Given a digraph G, the task is to determine if a vertex v is reachable from another vertex `s` for all pairs of `(s, v)` in the given graph.

<br/>

![](dfs_reachability.jpeg)
{ thumbnail="true" width="900"}

</tab>
<tab title="DFS">

> The DFS algorithm starts at the root node and explores as far as possible along each branch before backtracking. So, it starts at node 0 and goes to node 1, then to node 2, and then backtracks to node 1 and then to node 0.
> 
{ style="note" }

![](dfs_depths.png)
{ thumbnail="true" width="900" } 

>The algorithm follows the following steps:
>
> 1. Start by putting any one of the graph's vertices on top of a stack.
> 2. Take the top item of the stack and add it to the result list.
> 3. Create a list of that vertex's adjacent nodes. Add the ones which aren't in the visited list of nodes to the top of the stack.
> 4. Keep repeating steps 2 and 3 until the stack is empty.
> 5. The result list contains the DFS traversal of the graph.
> 6. The time complexity of the DFS algorithm is represented in the form of O(V + E), where V is the number of nodes and E is the number of edges.
> 7. The space complexity of the algorithm is O(V).
> 8. The algorithm is implemented using a stack data structure.

</tab>
<tab title="Directed-DFS">

**To visit vertex `v`**

Mark vertex `v`

Recursively visit all unmarked vertices adjacent from `v`

<br/>

![](https://he-s3.s3.amazonaws.com/media/uploads/9fa1119.jpg)
{ thumbnail="true" width="900" }
</tab>
<tab title="Properties">

> **Proposition**
> 
> DFS marks all vertices reachable from `s` in Theta(`E + V`) time in worst case

<br/>

> **Proof**
>
> Initializing an array of length `v` takes time Theta(`V`)  
> Each vertex is visited at most once  
> Visiting a vertex takes time proportional to its outdegree:  
> ```tex
> outdegree(v_0) + outdegree(v_1) + \ldots + outdegree(v_{V-1}) = E  \\
> ```
> ```tex
> \text{ in worst case, all } V \text{ vertices are reachable from } s
> ```

*_Note:_*

If all vertices are reachable from `s`, then `E >= V - 1`, so `V` is a lower-order term

</tab>
</tabs>
</procedure>

## Path Finding

<procedure>
<tabs>
<tab title="Terminology">

<table>
  <tr>
    <td>Self-loop</td>
    <td>an edge that connects a vertex to itself.</td>
  </tr>
  <tr>
    <td>Parallel edges</td>
    <td>Two edges are parallel if they connect the same ordered pair of vertices.</td>
  </tr>
  <tr>
    <td>out-degree (of a vertex)</td>
    <td>the number of edges pointing from it.</td>
  </tr>
  <tr>
    <td>in-degree (of a vertex)</td>
    <td>the number of edges pointing to it.</td>
  </tr>
  <tr>
    <td>Subgraph</td>
    <td>a subset of a digraph's edges (and associated vertices) that constitutes a digraph.</td>
  </tr>
  <tr>
    <td>Directed path</td>
    <td>a sequence of vertices in which there is a (directed) edge pointing from each vertex in the sequence to its successor in the sequence, with no repeated edges.</td>
  </tr>
  <tr>
    <td>Simple directed cycle</td>
    <td>A directed path is simple if it has no repeated vertices.</td>
  </tr>
  <tr>
    <td>Directed cycle</td>
    <td>a directed path (with at least one edge) whose first and last vertices are the same.</td>
  </tr>
  <tr>
    <td>Simple directed cycle</td>
    <td>if it has no repeated vertices (other than the requisite repetition of the first and last vertices).</td>
  </tr>
  <tr>
    <td>Length (of a path or a cycle)</td>
    <td>its number of edges.</td>
  </tr>
  <tr>
    <td>Strongly connected</td>
    <td>
        if two vertices are mutually reachable: there is a directed path from `v` to `w` and a directed path from `w` to `v`.
    </td>
  </tr>
</table>


<table>
<tr>
<td>

![](https://algs4.cs.princeton.edu/42digraph/images/digraph-anatomy.png)
{ thumbnail="true" width="900" }
</td>
<td>

![](https://algs4.cs.princeton.edu/42digraph/images/strong-components.png)
{ thumbnail="true" width="900" }
</td>
</tr>
</table>


</tab>
<tab title="Directed Path">

> **Goal**
>
> determine which vertices are reachable from a given vertex `s`

> **Solution**
>
> Use parent-link representation

<table>
<tr>
<td>

![parent-link](dfs_parent_link.jpeg)
{ thumbnail="true" width="900" }
</td>
<td>

![parent-link](dfs_parent_link_2.jpeg)
{ thumbnail="true" width="900" }
</td>
</tr>
</table>

> **Parent-Link Representation of paths to `s`**
>
> Maintain a vertex-indexed array `edgeTo[]` such that `edgeTo[v]` is the vertex from which `v` was visited
> 
{ style="note" }

</tab>
</tabs>
</procedure>

## Undirected Graphs

<procedure>
<tabs>
<tab title="Flood Fill">

> **Problem**
>
> Implement flood fill (Photoshop magic wand)

<br/>

![](https://static.wixstatic.com/media/bb1bd6_591167b0be9940758124b35badf1da3a~mv2.gif)
{ thumbnail="true" width="900" }

</tab>
<tab title="Graphs">

> **Problem**
> 
> Given a graph `G` and a vertex `s`, find all vertices connected to `s` in `G`

> **Solution**
>   
> Use depth-first search
> 
> Treat undirected graph as a digraph, replacing each edge with two antiparallel edges
> 
{ style="note" }

<br/>

```text 
dfs(G, s)
    mark s
    for each vertex w adjacent to s
        if w is not marked
            dfs(G, w)
```

<br/>

> **Typical applications**
> 
> Find all vertices connected to a given vertex  
> Find a path between two vertices
</tab>
<tab title="Undirected Search">

> **To visit vertex `v`**
>
> Mark vertex `v`
> Recursively visit all unmarked vertices adjacent from `v`

<br/>

<table>
<tr>
<td>

![](dfs_undirected_3.jpeg)
{ thumbnail="true" width="900" }
</td>
<td>

![](dfs_undirected_1.jpeg)
{ thumbnail="true" width="900" }

<deflist collapsible="true">
<def title="outcome">

![](dfs_undirected_2.jpeg)
{ thumbnail="true" width="900" }
</def>
</deflist>
</td>
<td>

![](dfs_undirected_4.jpeg)
{ thumbnail="true" width="900" }
</td>
</tr>
</table>
</tab>
<tab title="Search">

> Tree traversal
> 
> stack/recursion
> - inorder
> - preorder
> - postorder
> queue
> - level order

<table>
<tr>
<td>

```text
13
15
2 3 
0 6 
0 1 
2 0 
11 12  
9 12  
9 10  
9 11 
3 5 
8 7 
5 4 
0 5 
6 4 
6 9 
7 6
```

</td>
<td>

![](https://algs4.cs.princeton.edu/42digraph/images/depth-first-orders.png)
{ thumbnail="true" width="900" }
</td>
</tr>
</table>
</tab>
</tabs>
</procedure>

