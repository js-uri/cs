# Graphs

<video src="https://youtu.be/tq3zPnrQIpU" width="900" controls="true" />


## Definition

![graphs](https://media.geeksforgeeks.org/wp-content/uploads/20200630111809/graph18.jpg)
{ thumbnail="true" width="900"}

<table>
<tr>
<td colspan="2">Graph<br/>

a set of *_vertices_* connected pairwise by *_edges_*

<br/>


</td>
</tr>
<tr>
<td>

**Vertices**

- are just nodes
- each vertex (node)  


</td>
<td>

**Edges**

- connect any two vertices/nodes of the graph
- can be labeled or unlabeled

</td>

</tr>
</table>

### Examples

<table>
<tr>
<td>

**London Underground (Tube) Map**

<br/>

![](https://www.maureeneppstein.com/mve_journal/wp-content/uploads/underground-map1.gif)
{ thumbnail="true" width="300"}  

<br/>

vertex = subway stop  
edge = direct route
</td>
<td>

**Meta Social Network Map**

<br/>

![](https://revolution-computing.typepad.com/.a/6a010534b1db25970b0147e0ae51b2970b-800wi)
{ thumbnail="true" width="300"}

vertex = person;
edge = social relationship
</td>
</tr>
<tr>
<td>

**X Followers**

<br/>

![](https://allthingsgraphed.com/public/images/twitter/twitter-follower-graph-avatars.png)
{ thumbnail="true" width="300"}

<br/>

vertex = X account  
edge = X follower
</td>
<td>

**Protein-protein interation network**

<br/>

![](https://www.researchgate.net/publication/314491781/figure/fig5/AS:470414003576837@1489166846626/Protein-protein-network-analysis-based-on-regulated-genes-in-HEK293-cells-Interactions.png)
{ thumbnail="true" width="300"}

<br/>

vertex = protein  
edge = interaction
</td>
</tr>
</table>


## Types of Graphs

<table>

<tr>
<td>Graph Type</td>
<td>Definition</td>
<td>Example</td>
</tr>

<tr>
<td>Undirected Graph</td>
<td>An undirected graph is a graph in which edges have no orientation. The edge (u, v) is identical to the edge (v, u). An undirected graph is a graph consisting of a set of vertices and a set of edges in which the edges are unordered pairs of vertices.</td>
<td>

![](https://media.geeksforgeeks.org/wp-content/uploads/20230727130331/Undirected_to_Adjacency_matrix.png)
{ thumbnail="true" width="300"}

<br/>

![](https://media.geeksforgeeks.org/wp-content/uploads/20230727154843/Graph-Representation-of-Undirected-graph-to-Adjacency-List.png)
{ thumbnail="true" width="300"}
</td>
</tr>

<tr>
<td>Directed Graph</td>
<td>A directed graph is a graph in which edges have orientations. The edge (u, v) is not identical to the edge (v, u). A directed graph is a graph consisting of a set of vertices and a set of edges in which the edges are ordered pairs of vertices.</td>
<td>

![](https://media.geeksforgeeks.org/wp-content/uploads/20230727130528/Directed_to_Adjacency_matrix.png)
{ thumbnail="true" width="300"}

<br/>

![](https://media.geeksforgeeks.org/wp-content/uploads/20230727155209/Graph-Representation-of-Directed-graph-to-Adjacency-List.png)
{ thumbnail="true" width="300"}
</td>
</tr>

<tr>
<td>Weighted Graph</td>
<td>A weighted graph is a graph in which a weight is assigned to each edge. A weight can be any numerical value.</td>
<td>

![](https://media.geeksforgeeks.org/wp-content/uploads/labelled.png)
{ thumbnail="true" width="300"}
</td>
</tr>

<tr>
<td>Unweighted Graph</td>
<td>An unweighted graph is a graph in which no weight is assigned to any edge.</td>
</tr>

<tr>
<td>Cyclic Graph</td>
<td>A graph that has at least one cycle is called a cyclic graph.</td>
<td>

![](https://media.geeksforgeeks.org/wp-content/uploads/cyclic1.png)
{ thumbnail="true" width="300"}
</td>
</tr>

<tr>
<td>Acyclic Graph</td>
<td>A graph that has no cycle is called an acyclic graph.</td>
</tr>

<tr>
<td>Connected Graph</td>
<td>A graph is connected if there is a path between every pair of vertices.</td>
<td rowspan="2">

![](https://media.geeksforgeeks.org/wp-content/uploads/connected.png)   
{ thumbnail="true" width="300"}
</td>
</tr>

<tr>
<td>Disconnected Graph</td>
<td>A graph is disconnected if there is at least one pair of vertices for which there is no path between them.</td>
</tr>

<tr>
<td>Complete Graph</td>
<td>A graph is complete if there is an edge between every pair of vertices.</td>
<td>

![](https://media.geeksforgeeks.org/wp-content/uploads/complete1.png)
{ thumbnail="true" width="300"}

<br/>

![](https://media.geeksforgeeks.org/wp-content/uploads/complete2-1.png)
{ thumbnail="true" width="300"}
</td>
</tr>

</table>


## Graph Representation

<procedure>

<tabs>

<tab title="Digraph">

**Vertex Representation**

![](digraph_vertex.jpeg)
{ thumbnail="true" width="300" }

<br/>

**Defined**

![](digraph_def.jpeg)
{ thumbnail="true" width="300" }
</tab>    
<tab title="Adjacency Matrix">

![](https://media.geeksforgeeks.org/wp-content/uploads/20230727130331/Undirected_to_Adjacency_matrix.png)
{ thumbnail="true" width="300" }

<br/>

> For each edge `v -> w` in the digraph

![](https://media.geeksforgeeks.org/wp-content/uploads/20230727130528/Directed_to_Adjacency_matrix.png)
{ thumbnail="true" width="300" }

</tab>
<tab title="Adjacency List">

![](https://media.geeksforgeeks.org/wp-content/uploads/20230727154843/Graph-Representation-of-Undirected-graph-to-Adjacency-List.png)
{ thumbnail="true" width="300" }

<br/>

> Maintain vertex-indexed array of lists

![](https://media.geeksforgeeks.org/wp-content/uploads/20230727155209/Graph-Representation-of-Directed-graph-to-Adjacency-List.png)
{ thumbnail="true" width="300" }

</tab>
<tab title="In Practice">

**Use adjacency-lists**

Algorithms based on iterating over vertices adjacent from `v`

Real-world graphs tend to be sparce Theta(V) edges, not dense Theta(V^2) edges

<table>
<tr>
<td>Representation</td>
<td>Space</td>
<td>

add edge from `v -> w`
</td>
<td>

has edge from `v -> w`
</td>
<td>
iterate over vertices adjacent from `v`?
</td>
</tr>
<tr>
<td>Adjacency Matrix</td>
<td><code-block lang="tex"> V^2</code-block></td>
<td>1*</td>
<td>1</td>
<td><code-block lang="tex"> V</code-block></td>
</tr>
<tr>
<td>Adjacency List</td>
<td><code-block lang="tex"> E + V</code-block></td>
<td>1</td>
<td><code-block lang="tex"> outdegree(v)</code-block></td>
<td><code-block lang="tex"> outdegree(v)</code-block></td>
</tr>
</table>

* *_disallows parallel edges_*

</tab>
</tabs>

</procedure>
