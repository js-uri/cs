# Hash Tables

<show-structure for="chapter,procedure" depth="2"/>

<video src="https://youtu.be/knV86FlSXJ8?feature=shared" preview-src="hash-table.png" mini-player="true" width="900"/>



## Definition

<table>
<tr>
<td>
<note>
<p>A hash table is a data structure that implements an associative array abstract data type, a structure that can map keys to values. It uses a hash function to compute an index into an array of buckets or slots, from which the desired value can be found. The primary goal of a hash table is to provide efficient and constant-time average case access to elements.</p>
</note>
</td>
<td>
<img src="https://s3.ap-south-1.amazonaws.com/s3.studytonight.com/tutorials/uploads/pictures/1604593128-76844.png" 
alt="image"/>
</td>
</tr>
</table>




### Use Cases

<table>
<tr>
<td width="50%">
<img src="https://user-images.githubusercontent.com/38887077/76482821-4ec64780-6450-11ea-862e-da506f5cdae2.png" 
alt="image"/>
</td>
<td>
<img src="ht.jpeg" alt="image"/>
</td>
</tr>
<tr>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Database Indexing">Hash tables are commonly used in database indexing. The database engine uses a hash function to map keys (such as primary or unique keys) to index locations, allowing for quick retrieval of records.
</def>
</deflist>
</td>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Caching Systems">Hash tables are used in caching systems to quickly locate and retrieve cached data based on a key. This enhances the performance of systems by avoiding redundant computation.
</def>
</deflist>
</td>
</tr>
</table>

<table>
<tr>
<td>
<img src="https://iq.opengenus.org/content/images/2021/12/12.png" alt="image"/>
</td>
<td>
<img src="https://blog.superhosting.bg/wp-content/uploads/2017/12/en-dns-resolver-dns-juorney-03.png" alt="image"/>
</td>
<td>
<img src="https://media.geeksforgeeks.org/wp-content/uploads/20230331120006/Distributed-System.png" alt="image"/>
</td>
</tr>
<tr>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Compiler Symbol Tables">In compilers, hash tables are used to implement symbol tables. Identifiers in a program are hashed to quickly look up information such as data types or memory locations.
</def>
</deflist>
</td>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="DNS Resolution">Hash tables are employed in Domain Name System (DNS) resolution. They help in mapping domain names to IP addresses, facilitating efficient and quick lookup.
</def>
</deflist>
</td>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Distributed Systems">In distributed systems, hash tables are often used for consistent hashing, ensuring that data is evenly distributed across nodes, minimizing the impact of adding or removing nodes.
</def>
</deflist>
</td>
</tr>
</table>



### Advantages &amp; Disadvantages

<table>
<tr>
<td>✅</td>
<td>❌</td>
</tr>
<tr>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Fast Retrieval">Hash tables provide constant-time average case access to elements, making them efficient for retrieval operations.
</def>
<def title="Dynamic Size">Hash tables can dynamically resize themselves to accommodate a changing number of elements, ensuring efficiency even as the dataset grows or shrinks.
</def>
<def title="Flexible Key Types">Hash tables can handle a variety of key types, not just integers. This flexibility makes them suitable for a wide range of applications.
</def>
</deflist>
</td>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Collision Handling">Collisions can occur when multiple keys hash to the same index. Efficient collision resolution strategies are necessary to maintain performance.
</def>
<def title="Memory Overhead">Hash tables may consume more memory than other data structures, especially if the load factor is high or if chaining is used for collision resolution.
</def>
<def title="Not Ordered">Hash tables do not maintain any order among elements. If the order of insertion or retrieval is important, other data structures like linked lists or trees might be more suitable.
</def>
</deflist>
</td>
</tr>
</table>



### Why not?

<table>
<tr>
<td>
<img src="https://miro.medium.com/max/970/1*f2oDQ0cdY54olxCFOIMIdQ.png" alt="image"/><br/>
</td>
<td>
<img src="https://i.ytimg.com/vi/T4gyaR4lSxQ/maxresdefault.jpg" alt="image"/>
</td>
<td>
<img src="https://www.kindsonthegenius.com/wp-content/uploads/2020/09/Direct-Address-Table-1.jpg" alt="image"/><br/>
</td>
</tr>
<tr>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Arrays &amp; Linked-Lists">
<procedure title="" type="choices">
<p>Search</p> <code-block lang="tex"> O(log\ n)</code-block>
<p>Insert/Delete</p> <code-block lang="tex"> much\ more\ costly</code-block>
</procedure>
</def>
</deflist>
</td>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Binary Search Trees">
<procedure title="" type="choices">
<p>Guaranteed</p> <code-block lang="tex"> O(log\ n)</code-block>
</procedure>
</def>
</deflist>
</td>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Direct Access Table">
<procedure title="" type="choices">
<p>Best-case</p>
<p>Practical limitations</p>
<step>Extra space</step>
<step>A given integer in a programming language may not store 
 digits</step>
<step>Therefore, not always a viable option</step>
</procedure>
</def>
</deflist>
</td>
</tr>
</table>



## Hash Functions

<table style="none">
<tr>
<td width="900" colspan="2">
<list style="bullet">
<li>a function converting a piece of data into a smaller, more practical integer</li>
<li>the integer value is used as the <code>index</code> between <code>0</code> and <code>m - 1</code> for the 
data in the hash 
table
</li>
<li>ideally, maps all keys to a unique slot <code>index</code> in the table</li>
<li>perfect hash functions may be difficult, but not impossible to create</li>
</list>
</td>
</tr>
<tr>
<td colspan="2">
<img src="https://www.vladimircicovic.com/content/images/20200502181417-hash_function.jpg" alt="image" width="900"/>
</td>
</tr>
<tr>
<td>
<p><b>Properties of good hash functions</b></p>
<p>Efficiently computable</p>
<list style="bullet">
<li>Should uniformly distribute the keys (each table position equally likely for each)</li>
</list>
</td>
<td>
<br/>
<p>Load Balancing</p>
<list>
<li>Should minimize collisions</li>
<li>Should have a low load factor
<code-block lang="tex">
    \begin{equation}
    \frac{\#\ items\ in\ table}{table\ size}
    \end{equation}
</code-block>
</li>
</list>
</td>
</tr>
</table>



### Modular Hashing

<p><b>To uniformly create hashes, hash functions may use heuristic techniques of division or multiplication</b></p>

<table>
<tr>
<td>
    <p>Legend</p><br/>
    <table>
    <tr><td><code-block lang="tex"> h</code-block></td>    <td>hash function</td></tr>
    <tr><td><code-block lang="tex"> k</code-block></td>    <td>key</td></tr>
    <tr><td><code-block lang="tex"> HT</code-block></td>    <td>hash table</td></tr>
    <tr><td><code-block lang="tex"> m</code-block></td>    <td>table size</td></tr>
    <tr><td><code-block lang="tex"> b</code-block></td>    <td>bucket</td></tr>
    <tr><td><code-block lang="tex"> r</code-block></td>    <td>items per bucket</td></tr>
    </table>
</td>
<td>
    <p>Rules</p><br/>   
    <code-block lang="tex">
    \begin{align}
    0 \le h(k_x) \lt m\ , or \\ 
    0 \le h(k_x) \lt b-1 \\
    \\
    \\
    Entry\ lookup \Rightarrow HT[h(x)]
    \end{align}
    </code-block>
</td>
<td>
<p>Syntax</p>
<code-block lang="tex">
\begin{align}
h(k_x) &amp; = k_x\ mod\ m \\
&amp; = k_x\ \%\ m
\end{align}
</code-block>
</td>
</tr>
</table>

<table>
<tr>
<td>
<p>Example</p><br/>
<p>Suppose there are six students:</p>
<code-block lang="tex">
\begin{align}
a1, a2, a3, a4, a5, a6 \\\\
\end{align}</code-block>
<br/>
<p>in a Data Structures class and their IDs are:</p>

<code-block lang="tex">
    \begin{align}
    \\
    \bullet \ \ a1:   &amp; 197354863; \\
    \end{align}
    </code-block><br/>
<code-block lang="tex">
    \begin{align}
    \bullet \ \ a2:   &amp; 933185952; \\
    \end{align}
    </code-block><br/>
<code-block lang="tex">
    \begin{align}
    \bullet \ \ a3:   &amp; 132489973; \\
    \end{align}
    </code-block><br/>
<code-block lang="tex">
    \begin{align}
    \bullet \ \ a4:   &amp; 134152056; \\
    \end{align}
    </code-block><br/>
<code-block lang="tex">
    \begin{align}
    \bullet \ \ a5:   &amp; 216500306; \\
    \end{align}
    </code-block><br/>
<code-block lang="tex">
    \begin{align}
    \bullet \ \ a6:   &amp; 106500306; \\
    \end{align}
    </code-block><br/>
</td>
<td>
<p>Syntax</p><br/>
<code-block lang="tex">
\begin{align}
h: \{k_1,k_2,k_3,k_4,k_5,k_6 \} \rightarrow \\
\end{align}
</code-block>
<br/>
<code-block lang="tex">
\begin{align}
\{0,1,2,...12\}\ by\ h(k_1) = k_1 \%\ 13 \\
\end{align}
</code-block>
<br/><br/>
<code-block lang="tex">
\begin{align} 
h(k_1) &amp; = 197354863\ \%\ 13 &amp; = 4 \\ 
h(k_2) &amp; = 933185952\ \%\ 13 &amp; = 10 \\
h(k_3) &amp; = 132489973\ \%\ 13 &amp; = 5 \\
h(k_4) &amp; = 134152056\ \%\ 13 &amp; = 12 \\
h(k_5) &amp; = 216500306\ \%\ 13 &amp; = 9 \\
h(k_6) &amp; = 106500306\ \%\ 13 &amp; = 3 \\
\end{align}
</code-block>
</td>
<td>
<p>Outcome</p><br/>
<code-block lang="tex">
\begin{align}
Suppose\ HT[b] \leftarrow a
\end{align}
</code-block><br/><br/><br/>
<code-block lang="tex">
\begin{align}
HT[3] \leftarrow 106500306 \\
HT[4] \leftarrow 197354863 \\ 
HT[5] \leftarrow 132489973 \\
HT[9] \leftarrow 216500306 \\
HT[10] \leftarrow 933185952 \\
HT[12] \leftarrow 134152056 \\
\end{align}
</code-block>
</td>
</tr>
</table>



### Uniform Hashing

<table style="none">
<tr>
<td rowspan="3">
<deflist>
<def title="Assumption">Any key is equally likely (and independent of other keys) to hash to one of <code>m</code> possible indices
</def>
<def title="Bins and Balls">Toss <code>n</code> balls uniformly at random into <code>m</code> bins
</def>
<def title="Bad News [birthday problem]">
In a random group of 23 people, more likely than not that two people share the same birthday Expect two balls in the same bin after
<code-block lang="tex">
\begin{align}
\sim \sqrt{\pi * \frac{m}{2}} \ \ \ \ \ \ \ \ \ \ // = 23.9\ when\ m = 365
\end{align}
</code-block>
</def>
<def title="Good News">
when <code>n >> m</code>, expect most bins to have 
<code-block lang="tex">
\begin{align}
\approx \frac{n}{m} balls
\end{align}
</code-block>
<br/>
when <code>n = m</code>, expect most loaded bin has
<code-block lang="tex">
\begin{align}
\sim \frac{ln\ n}{ln\ ln\ n} balls
\end{align}
</code-block>
</def>
</deflist>
</td>
<td>
<img src="https://oddathenaeum.com/wp-content/uploads/2021/07/images-inside-post-thebirthdayparadox-1-1536x949.jpg" 
alt="image"/>
</td>
</tr>
<tr>
<td>
<img src="https://miro.medium.com/v2/resize:fit:1280/1*E2mZS9RtXxuL0i_o284CAg.png" alt="image"/>
</td>
</tr>
<tr>
<td>
<img src="https://academy.horizen.io/assets/post_files/technology/expert/2.2-hash-functions/birthday-problem_M.jpg" 
alt="image"/>
</td>
</tr>
</table>



## Collisions

<table>
<tr>
<td>
<procedure title="" type="choices">
<p>Two distinct keys that hash to the same index birthday problem</p>
<step>can’t avoid collisions</step>
</procedure>
<procedure title="" type="choices">
<p>load balancing</p>
<step>no index gets too many collisions</step>
<step>ok to scan though all colliding keys</step>
</procedure>
</td>
<td>
<img src="https://www.log2base2.com/images/algo/hash-collision.png" alt="image"/>
</td>
</tr>
</table>



## Separate Chaining

<procedure>
<p>Simple Uniform Hashing</p>
    <step>keeps a list of all elements that hash to the same value</step>
</procedure>

<table>
<tr>
<td>
<code-block lang="tex">
\begin{align}
m = 
\end{align}
</code-block> Number of slots in hash table
<br/>
<code-block lang="tex">
\begin{align}
n = 
\end{align}
</code-block> Number of keys to be inserted in hash table
</td>
<td>
<p>Load factor</p>
<code-block lang="tex">
\begin{align}
\alpha = \frac{n}{m} \\
\end{align}
</code-block><br/><br/>
<p>Expected time to search or delete</p>
<code-block lang="tex">
\begin{align}
O(1 + α)
\end{align}
</code-block>
</td>
<td>
<p>Time to insert</p> 
<code-block lang="tex">O(1)</code-block><br/><br/>
<p>Time complexity of search, insert, and delete is</p>
<code-block lang="tex">O(1)\ if\  α\ is\ O(1)</code-block>
</td>
</tr>
</table>

<table>
<tr>
<td>
<p>Example</p><br/>
<code-block lang="tex"> h : \{0,81,64,25,36,49,1,4,16,9 \}</code-block><br/>
<code-block lang="tex">
\begin{align}
h(k_1) &amp;= 0\ \%\ 10 &amp;= 0\ &amp;\Rightarrow\ \ \ \ \ HT[0] \leftarrow 0 \\
h(k_2) &amp;= 81\ \%\ 10  &amp;= 1\ &amp;\Rightarrow\ \ \ \ \ HT[1] \leftarrow 81 \\
h(k_3) &amp;= 64\ \%\ 10  &amp;= 4\ &amp;\Rightarrow\ \ \ \ \ HT[4] \leftarrow 64 \\ 
h(k_4) &amp;= 25\ \%\ 10 &amp;= 5\ &amp;\Rightarrow\ \ \ \ \ HT[5] \leftarrow 25 \\
h(k_5) &amp;= 36\ \%\ 10 &amp;= 6\ &amp;\Rightarrow\ \ \ \ \ HT[6] \leftarrow 36 \\
h(k_6) &amp;= 49\ \%\ 10 &amp;= 9\ &amp;\Rightarrow\ \ \ \ \ HT[9] \leftarrow 49 \\ 
h(k_7) &amp;= 1\ \%\ 10 &amp;= 1\ &amp;\Rightarrow\ \ \ \ \ HT[1] \leftarrow 1 \\
h(k_8) &amp;= 4\ \%\ 10 &amp;= 4\ &amp;\Rightarrow\ \ \ \ \ HT[4] \leftarrow 4 \\
h(k_9) &amp;= 16\ \%\ 10 &amp;= 6\ &amp;\Rightarrow\ \ \ \ \ HT[6] \leftarrow 16 \\
h(k_{10}) &amp;= 9\ \ \%\ 10 &amp;= 9\ &amp;\Rightarrow\ \ \ \ \ HT[9] \leftarrow 9 \\
\end{align}
</code-block>
</td>
<td>
<img src="https://www.researchgate.net/profile/Tribikram-Pradhan/publication/283760058/figure/fig2/AS:318584157949953
@1452967790509/Example-of-Separate-Chaining-Method.png" alt=""/>
</td>
</tr>
</table>



## Open Addressing

<procedure type="choices">
<step>If a collision occurs, search for the next available slot in a linear manner.</step>
</procedure>


### Linear Probing

<table>
<tr>
<td colspan="2">keeps a list of all elements that hash to the same value</td>
</tr>
<tr>
<td>
<procedure type="choices">
<p>Rule</p>
<code-block lang="tex"> h_i(x) = (Hash(x) + i) \ \% \ HashTableSize</code-block>
<p>If:</p>
<step><code-block lang="tex"> h_0(x) = (Hash(x) + 0) \ \% \ HashTableSize</code-block></step>
<step><code-block lang="tex"> h_1(x) = (Hash(x) + 1) \ \% \ HashTableSize</code-block></step>
<step><code-block lang="tex"> h_2(x) = (Hash(x) + 2) \ \% \ HashTableSize</code-block></step>
</procedure>
</td>
<td>
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2015/08/openAddressing1.png" alt="image"/>
</td>
</tr>
<tr>
<td>
<p>Example</p>
<code-block lang="tex"> h : \{50, 700, 76, 85, 92, 73, 101\}</code-block>
<code-block lang="tex"> 
\begin{align}
h_0(50) &amp;= 50\ \ \ \ \% \ 7 = 1 \\ \\
h_0(700) &amp;= 700\ \  \% \ 7 = 0 \\ \\
h_0(76) &amp;= 76\ \ \  \% \ 7 \ = 6 \\ \\
h_0(85) &amp;= 85\ \ \ \% \ 7 \  = 1 \\
&amp;\Rightarrow h_1(85) = (85+1)\ \ \%\ 7 = 2 \\
\end{align}
</code-block>
</td>
<td>
<code-block lang="tex"> 
\begin{align}
h_0(92) &amp;= 92\ \ \%\ 7 = 1 \\
&amp;\Rightarrow h_1(92) = (92+1)\ \ \%\ 7  = 1 \\
&amp;\Rightarrow h_2(92) = (92+2)\ \ \%\ 7  = 3 \\
\\
h_0(73) &amp;= 73\ \  \%\ 7  = 3 \\
&amp;\Rightarrow h_1(73) = (73+1)\ \  \%\ 7  = 4 \\
\\
h_0(101) &amp;= 101\ \  \%\ 7  = 3 \\
&amp;\Rightarrow h_1(101) = (101+1)\ \ \%\ 7  = 4 \\
&amp;\Rightarrow h_2(101) = (101+2)\ \ \%\ 7  = 5 \\
\end{align}
</code-block>
</td>
</tr>
</table>


### Quadratic Probing

<table>
<tr>
<td>
<p><b>RULE</b></p>
<br/>
<code-block lang="tex">
\begin{align}
h_i(x) &amp;= (Hash(x) + i^2)\ \%\ \ HashTableSize \\
&amp;\Rightarrow (Hash(x) + i*i)\ \%\ \ HashTableSize \\ \\
If\ h_0(x) &amp;= (Hash(x) + 0^0)\ \%\ \ HashTableSize \\
If\ h_1(x) &amp;= (Hash(x) + 1^1)\ \%\ \ HashTableSize \\
If\ h_2(x) &amp;= (Hash(x) + 2^2)\ \%\ \ HashTableSize \\
&amp;... and\ so\ on\ if\ h_i\ is\ already\ full...
\end{align}
</code-block>
</td>
<td>
<p><b>EXAMPLE</b></p>
<br/>
<code-block lang="tex">
\begin{align}
&amp;h : \{50, 700, 76, 85, 92, 73, 101\} &amp;\\
\\
\\
h_0(50) &amp;= 50\ \ \ \ \% \ 7 &amp;= 1 \\
h_0(700) &amp;= 700\ \  \%\ 7  &amp;= 0 \\
h_0(76) &amp;= 76\ \  \%\ 7  &amp;= 6 \\
h_0(85) &amp;= 85\ \ \%\ 7  &amp;= 1 \\
&amp;\Rightarrow h_1(85) = 85+(1*1)\ \ \%\ 7  &amp;= 2 \\
h_0(92) &amp;f= 92\ \ \%\ 7  = 1 \\
&amp;\Rightarrow h_1(92) = 92+(1*1)\ \ \%\ 7  &amp;= 2 \\
&amp;\Rightarrow h_2(92) = 92+(2*2)\ \ \%\ 7  &amp;= 5 \\
h_0(73) &amp;= 73\ \  \%\ 7  &amp;= 3 \\
h_0(101) &amp;= 101\ \  \%\ 7  &amp;= 3 \\
&amp;\Rightarrow h_1(101) = 101+(1*1)\ \  \%\ 7  &amp;= 4 \\
\end{align}
</code-block>
</td>
</tr>
</table>



### Double Hashing

<table style="none">
<tr>
<td>
<p><b>RULES</b></p>
<br/>
<code-block lang="tex">
    \begin{align}
    H_a(x) &amp;= Hash_1(x)\ \%\ Table\ Size \\
    H_b(x) &amp;= Hash_2(x)\ \%\ Table\ Size \\
    \\
    h(k, i) &amp;= \bigg[h_{a}(k) + i * h_{b}(k) \bigg] \ \% \ n \\
    \end{align}
</code-block>
<br/>
<br/><br/><br/>
<p><b>EXAMPLE</b></p>
<br/>
<code-block lang="tex">
    \begin{align}
    h : \{50, 700, 76, 85, 92, 73, 101\} \\
    size : 7
    \end{align}
</code-block>
</td>
<td>
<tabs>
<tab title="50">
<table style="none">
<tr>
<td>
<code-block lang="tex">
\begin{align}
h_0(50) &amp;= 50\ \% \ 7 \\
&amp; = 1 \\
\end{align}
</code-block>
</td>
<td>
    <table>
    <tr>
    <td>Key</td>
    <td>Value</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[0]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[1]
    \end{align}
    </code-block>
    </td>
    <td>50</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[2]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[3]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[4]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[5]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[6]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    </table>
</td>
</tr>
</table>
</tab>
<tab title="700">
<table style="none">
<tr>
<td>
<code-block lang="tex">
\begin{align}
h_0(700) &amp;= 700\ \%\ 7 \\
&amp;= 0 \\ \\
\end{align}
</code-block>
</td>
<td>
    <table>
    <tr>
    <td>Key</td>
    <td>Value</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[0]
    \end{align}
    </code-block>
    </td>
    <td>700</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[1]
    \end{align}
    </code-block>
    </td>
    <td>50</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[2]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[3]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[4]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[5]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[6]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    </table>
</td>
</tr>
</table>
</tab>
<tab title="76">
<table style="none">
<tr>
<td>
<code-block lang="tex">
\begin{align}
h_0(76) &amp;= 76\ \%\ 7 \\
&amp; = 6 \\
\end{align}
</code-block>
</td>
<td>
    <table>
    <tr>
    <td>Key</td>
    <td>Value</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[0]
    \end{align}
    </code-block>
    </td>
    <td>700</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[1]
    \end{align}
    </code-block>
    </td>
    <td>50</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[2]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[3]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[4]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[5]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[6]
    \end{align}
    </code-block>
    </td>
    <td>76</td>
    </tr>
    </table>
</td>
</tr>
</table>
</tab>
<tab title="85">
<table style="none">
<tr>
<td>
<code-block lang="tex">
\begin{align}
h_0(85) &amp;= 85\ \ \%\ 7  = 1 \\
h_1(85) &amp;= \bigg[ h_{a}(85) + i * h_{b}(85) \bigg] \ \% \ 7 \\
&amp;= \bigg[1 + 1 * (85\ \% \ 7) \bigg] \ \% \ 7 \\
&amp;= \bigg[1 + 1 * 1 \bigg] \ \% \ 7 \\ 
&amp;= 2 \\
\end{align}
</code-block>
</td>
<td>
    <table>
    <tr>
    <td>Key</td>
    <td>Value</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[0]
    \end{align}
    </code-block>
    </td>
    <td>700</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[1]
    \end{align}
    </code-block>
    </td>
    <td>50</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[2]
    \end{align}
    </code-block>
    </td>
    <td>85</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[3]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[4]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[5]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[6]
    \end{align}
    </code-block>
    </td>
    <td>76</td>
    </tr>
    </table>
</td>
</tr>
</table>
</tab>
<tab title="92">
<table style="none">
<tr>
<td>
<code-block lang="tex">
\begin{align}
h_0(92) &amp;= 92\ \ \%\ 7  = 1 \\
h_1(92) &amp;= \bigg[ h_{a}(92) + i * h_{b}(92) \bigg] \ \% \ 7 \\
&amp;= \bigg[1 + 1 * (92\ \% \ 7) \bigg] \ \% \ 7 \\
&amp;= \bigg[1 + 1 * 1 \bigg] \ \% \ 7 \\ 
&amp;= 2 \\
h_2(92) &amp;= \bigg[ h_{a}(92) + i * h_{b}(92) \bigg] \ \% \ 7 \\
&amp;= \bigg[1 + 2 * (92\ \% \ 7) \bigg] \ \% \ 7 \\
&amp;= \bigg[1 + 2 * 1 \bigg] \ \% \ 7 \\ 
&amp;= 3 \\
\end{align}
</code-block>
</td>
<td>
    <table>
    <tr>
    <td>Key</td>
    <td>Value</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[0]
    \end{align}
    </code-block>
    </td>
    <td>700</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[1]
    \end{align}
    </code-block>
    </td>
    <td>50</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[2]
    \end{align}
    </code-block>
    </td>
    <td>85</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[3]
    \end{align}
    </code-block>
    </td>
    <td>92</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[4]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[5]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[6]
    \end{align}
    </code-block>
    </td>
    <td>76</td>
    </tr>
    </table>
</td>
</tr>
</table>
</tab>
<tab title="73">
<table style="none">
<tr>
<td>
<code-block lang="tex">
\begin{align}
h_0(73) &amp;= 73\ \ \% \ 7  = 3 \\
h_1(73) &amp;= \bigg[ h_{a}(73) + i * h_{b}(73) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 1 * (73\ \% \ 7) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 1 * 3 \bigg] \ \% \ 7 \\ 
&amp;= 6 \\
h_2(73) &amp;= \bigg[ h_{a}(73) + i * h_{b}(73) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 2 * (73\ \% \ 7) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 2 * 3 \bigg] \ \% \ 7 \\ 
&amp;= 2 \\
h_3(73) &amp;= \bigg[ h_{a}(73) + i * h_{b}(73) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 3 * (73\ \% \ 7) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 3 * 3 \bigg] \ \% \ 7 \\ 
&amp;= 5 \\
\end{align}
</code-block>
</td>
<td>
    <table>
    <tr>
    <td>Key</td>
    <td>Value</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[0]
    \end{align}
    </code-block>
    </td>
    <td>700</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[1]
    \end{align}
    </code-block>
    </td>
    <td>50</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[2]
    \end{align}
    </code-block>
    </td>
    <td>85</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[3]
    \end{align}
    </code-block>
    </td>
    <td>92</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[4]
    \end{align}
    </code-block>
    </td>
    <td></td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[5]
    \end{align}
    </code-block>
    </td>
    <td>73</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[6]
    \end{align}
    </code-block>
    </td>
    <td>76</td>
    </tr>
    </table>
</td>
</tr>
</table>
</tab>
<tab title="101">
<table style="none">
<tr>
<td>
<code-block lang="tex">
\begin{align}
h_0(101) &amp;= 101\ \  \%\ 7  = 3 \\
h_1(101) &amp;= \bigg[ h_{a}(101) + i * h_{b}(101) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 1 * (101\ \% \ 7) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 1 * 3 \bigg] \ \% \ 7 \\ 
&amp;= 6 \\
h_2(101) &amp;= \bigg[ h_{a}(101) + i * h_{b}(101) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 2 * (101\ \% \ 7) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 2 * 3 \bigg] \ \% \ 7 \\ 
&amp;= 2 \\
h_3(101) &amp;= \bigg[ h_{a}(101) + i * h_{b}(101) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 3 * (101\ \% \ 7) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 3 * 3 \bigg] \ \% \ 7 \\ 
&amp;= 5 \\
h_4(101) &amp;= \bigg[ h_{a}(101) + i * h_{b}(101) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 4 * (101\ \% \ 7) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 4 * 3 \bigg] \ \% \ 7 \\ 
&amp;= 1 \\
h_5(101) &amp;= \bigg[ h_{a}(101) + i * h_{b}(101) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 5 * (101\ \% \ 7) \bigg] \ \% \ 7 \\
&amp;= \bigg[3 + 5 * 3 \bigg] \ \% \ 7 \\ 
&amp;= 4 \\
\end{align}
</code-block>
</td>
<td>
    <table>
    <tr>
    <td>Key</td>
    <td>Value</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[0]
    \end{align}
    </code-block>
    </td>
    <td>700</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[1]
    \end{align}
    </code-block>
    </td>
    <td>50</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[2]
    \end{align}
    </code-block>
    </td>
    <td>85</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[3]
    \end{align}
    </code-block>
    </td>
    <td>92</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[4]
    \end{align}
    </code-block>
    </td>
    <td>101</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[5]
    \end{align}
    </code-block>
    </td>
    <td>73</td>
    </tr>
    <tr>
    <td>
    <code-block lang="tex">
    \begin{align}
    Arr[6]
    \end{align}
    </code-block>
    </td>
    <td>76</td>
    </tr>
    </table>
</td>
</tr>
</table>
</tab>
</tabs>
</td>
</tr>
</table>



## Comparison

<img src="complexity.png" alt=""/>