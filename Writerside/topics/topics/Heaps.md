# Heaps

<video src="https://youtu.be/0wPlzMU-k00?feature=shared"/>



## max Heap

<a href="https://www.geeksforgeeks.org/difference-between-min-heap-and-max-heap/?ref=gcse">max Heap</a>

<table>
<tr>
<td width="300">
    <deflist>
    <def title="Structure Property">
    a heap is a <a href="https://www.geeksforgeeks.org/complete-binary-tree/"><i>complete binary tree</i></a>
    </def>
    <def title="Heap-Order Property">
    <procedure>
    <p>for every node <code>x</code></p>
    <step>key parent <code-block lang="tex"> x &ge; key\ x</code-block></step>
    <step>except the root, which has no parent</step>
    </procedure>
    </def>
    </deflist>
    <deflist>
    <def title="Height of a Heap">
    <code-block lang="tex"> n &ge; 2^h \Rightarrow log\ n &ge; log\ 2^h \Rightarrow log\ n &ge; 
h</code-block><br/>
    </def>
    </deflist>
</td>
<td>
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/20201106115254/MaxHeap.jpg" alt="max heap"/><br/>
    <p>What is the minimum number of nodes in a complete binary tree of height?</p>
</td>
</tr>
</table>

### Implementation

<table>
<tr>
<td colspan="4">
<img src="13_implement_1.png" alt="array"/>
</td>
</tr>
<tr>
<td colspan="4">
<img src="13_implement_2.png" alt="heap"/>
</td>
</tr>
<tr>
<td>
<b>node (i)</b><br/>
<code-block lang="tex"> \bullet \ \ \ \ \ i</code-block>
</td>
<td>
<b>parent (i)</b><br/>
<code-block lang="tex"> \bullet \ \ \ \ \ \lfloor \frac{i}{2} \rfloor</code-block>
</td>
<td>
<b>left child (i)</b><br/>
<code-block lang="tex"> \bullet \ \ \ \ \ i * 2</code-block>
</td>
<td>
<b>right child (i)</b><br/>
<code-block lang="tex"> \bullet \ \ \ \ \ i * 2 + 1</code-block>
</td>
</tr>
</table>



### Class functions

<table>
<tr>
<td>
<procedure title="insert" type="choices">
<p>Append new element to the end of array</p>
<p>Check heap-order property</p>
<step>if violated, Up-Heap (swap with parent); repeat until heap-order is restored</step>
<step>if not, <code>insert</code> complete</step>
</procedure>
</td>
<td>
<procedure title="removeMax" type="choices">
<p>Max element is the first element of the array</p>
<step>the <code>root</code> of the heap</step>
</procedure>
<procedure type="choices">
<p>Copy last element of array to the first position</p>
<step>then decrement array size by 1 (removes the last element)</step>
</procedure>
<procedure type="choices">
<p>Check heap-order property</p>
<step><code>if violated, Down-Heap (swap with larger child); repeat until heap-order is restored</code></step>
<step>if not, <code>insert</code> complete</step>
</procedure>
</td>
</tr>
<tr>
<td>
<b>Complexity</b><br/>
<code-block lang="tex">  \bullet \ \ \ \ \ O(log\ n)</code-block>
</td>
<td>
<b>Complexity</b><br/>
<code-block lang="tex"> \bullet \ \ \ \ \ O(log\ n)</code-block>
</td>
</tr>
</table>

### Performance

<table>
<tr>
<td></td><td>Sorted Collection</td><td>Unsorted Collection</td><td>Heap</td>
</tr>
<tr>
<td><code>insert</code></td><td><code-block lang="tex"> O(n)</code-block></td><td><code-block lang="tex"> O(1)</code-block></td><td><code-block lang="tex"> O(log\ n)</code-block></td>
</tr>
<tr>
<td><code>removeMax</code></td><td><code-block lang="tex"> O(1)</code-block></td><td><code-block lang="tex"> O(n)</code-block></td><td><code-block lang="tex"> O(log\ n)</code-block></td>
</tr>
<tr>
<td><code>max</code></td><td><code-block lang="tex"> O(1)</code-block></td><td><code-block lang="tex"> O(n)</code-block></td><td><code-block lang="tex"> O(1)</code-block></td>
</tr>
<tr>
<td><code>insert N</code></td><td><code-block lang="tex"> O(n^2)</code-block></td><td><code-block lang="tex"> O(n)</code-block></td><td><code-block lang="tex"> O(n)</code-block>**</td>
</tr>
</table>
<p><i>(**) assuming we know the sequence in advance (buildHeap)</i></p>
