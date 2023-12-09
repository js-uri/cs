# Left-Leaning Red-Black Trees

<show-structure for="chapter,procedure" depth="2"/>

<tabs>
    <tab title="Intro">
        <video src="https://youtu.be/qvZGUFHWChY?feature=shared" preview-src="intro_yt.jpeg" width="900" 
mini-player="true"/>
    </tab>
    <tab title="Rotations">
        <video src="https://youtu.be/95s3ndZRGbk?feature=shared" preview-src="rotations_yt.jpeg" width="705" mini-player="true"/>
    </tab>
    <tab title="Insertion {Strategy}">
        <video src="https://youtu.be/5IBxA-bZZH8?feature=shared" preview-src="insertions_strat_yt.png" width="705" 
mini-player="true"/>
    </tab>
    <tab title="Insertion {Examples}">
        <video src="https://youtu.be/A3JZinzkMpk?feature=shared" preview-src="insertions_ex_yt.jpeg" width="705" mini-player="true"/>
    </tab>
    <tab title="Deletions">
        <video src="https://youtu.be/lU99loSvD8s?feature=shared" preview-src="deletions_yt.png" width="705" mini-player="true"/>
    </tab>
    <tab title="Deletion Fixes">
        <video src="https://youtu.be/iw8N1_keEWA?feature=shared" preview-src="delete_fixes_yt.png" width="705" mini-player="true"/>
    </tab>
</tabs>



## Definition

<note>
<p>A left-leaning red-black tree is a self-balancing binary search tree that maintains balance through the 
use of coloring and rotation operations. In this variation of red-black trees, every edge is either red or black, and it satisfies the red-black properties, with an additional constraint that no right child of a node can be red.</p>
</note>



### Use Cases

<table>
<tr>
<td>
<procedure>
<img src="https://user-images.githubusercontent.com/38887077/76482821-4ec64780-6450-11ea-862e-da506f5cdae2.png" 
alt="image"/>
<p><b>Database Indexing</b></p>
<step>Efficient for indexing in databases, facilitating quick search and retrieval operations<br/></step>
</procedure>
</td>
<td>
<procedure>
<img src="https://www.bogotobogo.com/cplusplus/images/memoryallocation/memory_allocation_delete.png" alt="image"/>
<p><b>Memory Allocation</b></p>
<step>employed in memory allocators to maintain a balanced structure, optimizing memory access times</step>
</procedure>
</td>
<td>
<procedure>
<img src="https://smbmatters.files.wordpress.com/2012/01/network_routing.jpg?w=630" alt="image"/>
<p><b>Network Routing</b></p>
<step>Used in routing tables for efficient IP address lookup in network routers<br/><br/></step>
</procedure>
</td>
</tr>
</table>



### Advantages & Disadvantages

<table>
<tr>
<td>Advantages</td>
<td>Disadvantages</td>
</tr>
<tr>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Simpler Maintenance">
The left-leaning property simplifies the tree structure compared to traditional red-black trees
</def>
<def title="Balanced Operations">
Maintains a balanced structure, ensuring efficient search, insert, and delete operations
</def>
</deflist>

[//]: # (<procedure>)

[//]: # (<img src="https://smbmatters.files.wordpress.com/2012/01/network_routing.jpg?w=630" alt="image">)
[//]: # (<p><b>Simpler Maintenance</b></p>)

[//]: # (<step>The left-leaning property simplifies the tree structure compared to traditional red-black trees<br/></step>)

[//]: # (</procedure>)

[//]: # (<procedure>)

[//]: # (<img src="https://smbmatters.files.wordpress.com/2012/01/network_routing.jpg?w=630" alt="image">)
[//]: # (<p><b>Balanced Operations</b></p>)

[//]: # (<step>Maintains a balanced structure, ensuring efficient search, insert, and delete operations<br/><br/></step>)

[//]: # (</procedure>)
</td>
<td>

<deflist collapsible="true" default-state="collapsed">
<def title="Increased Memory Usage">
The additional color bit for each node increases memory overhead
</def>
<def title="Complex Implementation">
Implementing left-leaning red-black trees can be more complex than simpler data 
structures
</def>
</deflist>


[//]: # (<procedure>)

[//]: # (<img src="https://smbmatters.files.wordpress.com/2012/01/network_routing.jpg?w=630" alt="image">)
[//]: # (<p><b>Increased Memory Usage</b></p>)

[//]: # (<step>The additional color bit for each node increases memory overhead<br/><br/></step>)

[//]: # (</procedure>)

[//]: # (<procedure>)

[//]: # (<img src="https://smbmatters.files.wordpress.com/2012/01/network_routing.jpg?w=630" alt="image">)
[//]: # (<p><b>Complex Implementation</b></p>)

[//]: # (<step>Implementing left-leaning red-black trees can be more complex than simpler data )

[//]: # (structures<br/><br/></step>)

[//]: # (</procedure>)
</td>
</tr>
</table>



## Implementation

<note>
<procedure type="choices">
<p><b>Structure</b></p>
<p>A left-leaning red-black tree is a type of self-balancing binary search tree that maintains the following properties</p>
<step>Every node is colored either red or black</step>
<step>The root node is always black</step>
<step>Every leaf (null node) is considered black</step>
<step>If a node is red, both its children are black</step>
<step>Every path from a node to its descendant leaves contains the same number of black nodes</step>
</procedure>
</note>

<img src="http://www2.cs.ccu.edu.tw/~tmh104u/rotate5.png" alt=""/>
<img src="http://www2.cs.ccu.edu.tw/~tmh104u/rotate3.png" alt=""/>
























































