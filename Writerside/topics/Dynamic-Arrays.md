# Dynamic Arrays

<video src="https://youtu.be/MwwbgqG6bSk?feature=shared" width="900" mini-player="true"/>



## Interfaces &amp; Data Structures

<table>
<tr>
<td>
<procedure style="choices">
<b>Interface</b>
<step>In programming, an interface is a blueprint or contract that defines a set of methods or behaviors that a class must implement.</step>
<step>An interface specifies the method signatures (function declarations) and sometimes constants or properties that a class implementing the interface should provide.</step>
<step>Interfaces enable polymorphism and provide a way to define common behavior that multiple classes can adhere to.</step>
<step>In many programming languages, including Java and C#, interfaces are used to achieve abstraction and enforce a certain level of consistency and structure across related classes.</step>
</procedure>
</td>
<td>
<procedure style="choices">
<b>Data Structures</b>
<step>In programming, a data structure is a way of organizing and storing data to enable efficient manipulation and access.</step>
<step>Data structures define how data is organized, stored, and accessed in computer memory.</step>
<step>Different data structures are designed to handle specific types of data and perform operations such as insertion, deletion, searching, and sorting.</step>
<step>Common examples of data structures include arrays, linked lists, stacks, queues, trees, graphs, and hash tables.
</step>
</procedure>
</td>
</tr>
</table>



## Static Arrays

### Definition

<note>
<procedure style="choices">
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Array-In-C.png" alt=""/>
<step>An array is a contiguous sequence of elements of the same type</step>
<step>Each element can be accessed using an <code>index</code></step>
</procedure>
</note>

### Declaration

<procedure style="choices">
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Array-Declaration-In-C.png" alt=""/>

<deflist collapsible="true" default-state="collapsed">
<def title="Array declaration by specifying size">

```c++
// array declaration by specifying size  
int a[3];
```
</def>
<def title="Declare an array of user specified size">

```c++
// can also declare an array of user specified size
// (must be const for many compilers!)  
int s = 3;
int a[s];
```
</def>
<def title="Declare and initialize elements">

```c++
// can declare and initialize elements  
double arr[] = { 10.0, 20.0, 30.0, 40.0 };
// size is implicitly understood by the compiler 
// when initialized at declaration
```
</def>
<def title="Declare and initialize elements">

```c++
// alternative way  
int arr[5] = { 1, 2, 3 };
// size is explicitly manipulated for the compiler
// size = 5, element count = 3, empty elements remaining = 2 
```
</def>
<def title="What is the common theme in these array declarations?">
<warning>All of these declarations must have a size instantiated whether explicitly or implicitly...</warning>
</def>
</deflist>
</procedure>

[Try it...](https://pythontutor.com/iframe-embed.html#code=//%20Example%20C%2B%2B%20code%20for%20OPT%0Aint%20main%28%29%20%7B%0A%20%20float%20var1%3B%0A%20%20float%20var2%3B%0A%20%20int%20static_array%5B10%5D%3B%0A%20%20int%20*static_array_heap%20%3D%20new%20int%20%5B10%5D%3B%0A%20%20//%20...%0A%20%20//%20work%20with%20this%20array%0A%20%20//%20...%0A%20%20delete%20%5B%5D%20static_array_heap%3B%0A%20%20return%200%3B%0A%7D&amp;codeDivHeight=400&amp;codeDivWidth=350&amp;cumulative=false&amp;curInstr=0&amp;heapPrimitives=nevernest&amp;origin=opt-frontend.js&amp;py=cpp_g%2B%2B9.3.0&amp;rawInputLstJSON=%5B%5D&amp;textReferences=false)

## Static v. Dynamic Arrays

<table>
<tr>
    <th></th>
    <th>Static Arrays</th>
    <th>Dynamic Arrays</th>
</tr>
<tr>
    <td>Memory Allocation</td>
    <td>Fixed size at compile time</td>
    <td>Can dynamically resize during runtime</td>
</tr>
<tr>
    <td>Size Modification</td>
    <td>Fixed size, cannot be changed</td>
    <td>Size can be changed dynamically as needed</td>
</tr>
<tr>
    <td>Memory Management</td>
    <td>Less flexible, may lead to memory wastage</td>
    <td>Efficient memory usage, adapts to actual needs</td>
</tr>
<tr>
    <td>Access Time</td>
    <td>Constant time O(1)</td>
    <td>Constant time O(1) for random access, but may involve resizing which is O(n) on average</td>
</tr>
<tr>
    <td>Memory Location</td>
    <td>Contiguous block of memory</td>
    <td>Non-contiguous, allocated in heap</td>
</tr>
<tr>
    <td>Initialization</td>
    <td>Must specify size at the beginning</td>
    <td>Can start with a smaller size and grow as needed</td>
</tr>
<tr>
    <td>Complexity</td>
    <td>Simplicity in implementation</td>
    <td>More complex due to dynamic resizing</td>
</tr>
<tr>
    <td>Compile-Time Errors</td>
    <td>Detectable at compile time</td>
    <td>Runtime errors possible if size is exceeded</td>
</tr>
<tr>
    <td>Usage</td>
    <td>Suitable when size is known in advance</td>
    <td>Suitable when the size is unpredictable or may change dynamically</td>
</tr>
</table>



## Dynamic Arrays

<procedure style="choices">
<b>Dynamically allocated arrays that change their size over time</b>
<step>can <format color="GreenYellow">grow</format> and <format color="GreenYellow">shrink</format> automatically</step>
<step><img src="https://www.technotification.com/wp-content/uploads/2018/08/Screen-Shot-2018-08-03-at-3.21.32-PM-1024x287.png" alt=""/></step>
</procedure>

<table style="none">
<tr>
<td>

[//]: # (FIXME : ADD UML DIAGRAM BACK IN)
[//]: # (```plantuml)

[//]: # ()
[//]: # (@startuml)

[//]: # ()
[//]: # (class DynamicArray {)

[//]: # (- data : T*)

[//]: # (- size : size_t)

[//]: # (- capacity : size_t)

[//]: # (..)

[//]: # (+ DynmaicArray&#40;&#41;)

[//]: # (+ DynamicArray&#40;size_t initialSize&#41;)

[//]: # (+ DynamicArray&#40;const DynamicArray&amp;other&#41;)

[//]: # (+ ~DynamicArray&#40;&#41;)

[//]: # (+ operator=&#40;const DynamicArray&amp;other&#41;)

[//]: # (+ void pushBack&#40;const T&amp;element&#41;)

[//]: # (+ void popBack&#40;&#41;)

[//]: # (+ T&amp;operator[]&#40;size_t index&#41; const)

[//]: # (+ size_t getSize&#40;&#41; const)

[//]: # (+ size_t getCapacity&#40;&#41; const)

[//]: # (+ void resize&#40;size_t newSize&#41;)

[//]: # ()
[//]: # (..)

[//]: # ()
[//]: # (})

[//]: # ()
[//]: # (@enduml)

[//]: # ()
[//]: # (```)

<a href="https://en.cppreference.com/w/cpp/container/vector">CPPReference : std::vector</a>

</td>
<td>

<deflist collapsible="true" default-state="collapsed">
<def title="Key Elements">
    <deflist>
        <def title="data">
            <p>Pointer to the underlying array</p>
        </def>
        <def title="size">
            <p>Current number of elements in the array</p>
        </def>
        <def title="capacity">
            <p>Total capacity of the array</p>
        </def>
    </deflist>
</def>
</deflist>

<deflist collapsible="true" default-state="collapsed">
<def title="Public Methods">
    <deflist>
        <def title="DynamicArray()">
            <p>Default constructor</p>
        </def>
        <def title="DynamicArray(size_t initialSize)">
            <p>Constructor with an initial size</p>
        </def>
        <def title="DynamicArray(const DynamicArray&amp; other)">
            <p>Copy constructor</p>
        </def>  
        <def title="~DynamicArray()">
            <p>Destructor</p>
        </def>
        <def title="operator=(const DynamicArray&amp; other)">
            <p>Assignment operator</p>  
        </def>
        <def title="pushBack(const T&amp; element)">
            <p>Adds an element to the end</p>
        </def>
        <def title="popBack()">
            <p>Removes the last element</p>
        </def> 
        <def title="operator[](size_t index) const">
            <p>Overloaded subscript operator for element access</p>
        </def>
        <def title="getSize() const">
            <p>Returns the current size</p>
        </def>
        <def title="getCapacity() const">
            <p>Returns the current capacity</p>
        </def>
        <def title="resize(size_t newSize)">
            <p>Resizes the array</p>
        </def>
    </deflist>
</def>
</deflist>


<procedure style="choices">
<b>Operations on arrays</b>
<step><code-block lang="tex"> append\ :: \ ??</code-block></step>
<step><code-block lang="tex"> remove\ :: \ ??</code-block></step>
<step><code-block lang="tex"> get\ :: \Theta(1)</code-block></step>
<step><code-block lang="tex"> set\ :: \Theta(1)</code-block></step>
</procedure>

<deflist collapsible="true" default-state="collapsed">
    <def title="What are the time complexities of append and remove?">
        These will vary, based on where the event takes place.
    </def>
</deflist>
</td>
</tr>
</table>

<note>
<b>Background</b>
<p>Consider a dynamic array that needs to be resized when it reaches full capacity. Resizing involves creating a new array, copying elements from the old array to the new one, and deallocating the old array.
</p>
</note>

<deflist collapsible="true" default-state="collapsed">
<def title="Individual Operation Analysis">
<procedure style="choices">
<code-block lang="tex"> \text{Appending an Element : } O(1) </code-block>
<step><code-block lang="tex"> \text{Appending an element to the dynamic array typically takes constant time.} </code-block></step>
</procedure>
<procedure style="choices">
<code-block lang="tex"> \text{Resizing Operation : } O(n) </code-block>
<step>
<code-block lang="tex"> \text{Resizing, however, involves copying all elements from the old array  } </code-block><br/>
<code-block lang="tex"> \text{to the new array, which takes linear time proportional to the number } </code-block><br/>
<code-block lang="tex"> \text{number of elements in the array.} </code-block></step>
</procedure>
</def>
</deflist>

<deflist collapsible="true" default-state="collapsed">
<def title="Amortized Analysis">
<procedure style="choices">
<code-block lang="tex"> \text{Sequence of Operations} </code-block>
<step><code-block lang="tex"> \text{Suppose we perform a sequence of operations, where each operation} </code-block><br/>
<code-block lang="tex"> \text{ includes either appending an element or resizing.} </code-block></step>
</procedure>
<procedure style="choices">
<code-block lang="tex"> \text{Amortized Cost Calculation} </code-block>
<step><code-block lang="tex"> \text{The amortized cost is calculated as the total cost of the sequence } </code-block><br/>
<code-block lang="tex"> \text{divided by the number of operations.} </code-block></step>
</procedure>
<procedure style="choices">
<code-block lang="tex"> \text{Amortized Cost for Append : } Average = O(1) </code-block>
<step><code-block lang="tex"> \text{Most appends are } O(1), \text{ contributing a constant cost.} </code-block></step>
</procedure>
<procedure style="choices">
<code-block lang="tex"> \text{Occasional Resize : } Amortized = O(n) </code-block>
<step><code-block lang="tex"> \text{When a resize occurs, it incurs a cost of } O(n), </code-block><br/>
<code-block lang="tex"> \text{but this cost is spread across all the appends that necessitated the resize.} </code-block></step>
</procedure>
<procedure style="choices">
<code-block lang="tex"> \text{Amortized Analysis Result} </code-block>
<step><code-block lang="tex"> \text{Despite occasional } O(n) \text{ operations, the amortized cost } </code-block><br/>
<code-block lang="tex"> \text{per operation remains because the cost of resizing is } </code-block><br/>
<code-block lang="tex"> \text{distributed across multiple appends.} </code-block></step>
</procedure>
</def>
</deflist>

<deflist collapsible="true" default-state="collapsed">
<def title="Relevance of Amortized Analysis">
<procedure style="choices">
<code-block lang="tex"> \text{Smoothing Out Costs}</code-block>
<step><code-block lang="tex"> \text{Amortized analysis helps in smoothing out the costs of individual} </code-block><br/>
<code-block lang="tex"> \text{operations over a sequence, providing a more balanced view of the} </code-block><br/>
<code-block lang="tex"> \text{algorithm’s performance.} </code-block></step>
</procedure>
<procedure style="choices">
<code-block lang="tex"> \text{Ensuring Predictable Performance} </code-block>
<step><code-block lang="tex"> \text{It ensures that the average cost per operation remains reasonable,} </code-block><br/>
<code-block lang="tex"> \text{even if some operations are more expensive than others.} 
</code-block></step>
</procedure>
<procedure style="choices">
<code-block lang="tex"> \text{Use Cases} </code-block>
<step><code-block lang="tex"> \text{Amortized analysis is commonly applied to data structures like} </code-block><br/>
<code-block lang="tex"> \text{dynamic arrays, hash tables, and certain tree structures where occasional} </code-block><br/>
<code-block lang="tex"> \text{expensive operations are offset by a sequence of less expensive operations.} </code-block></step>
</procedure>
</def>
</deflist>

<tip>
<b>First, Try...</b>

<code-block lang="tex"> \text{Start wth an empty array} </code-block><br/>
<code-block lang="tex"> \text{For every } append </code-block>

- <code-block lang="tex"> \text{increase the size of the array by 1} </code-block>
- <code-block lang="tex"> \text{then write the new element} </code-block>

<code-block lang="tex"> \text{For every } remove\_last </code-block>

- <code-block lang="tex"> \text{remove the last element } </code-block>
- <code-block lang="tex"> \text{then decrease the size of the array by 1} </code-block>
</tip>


## Analyzing Cost

<tabs>
<tab title="Grow by 1">

<procedure>
<code-block lang="tex"> \text{Count array accesses (reads and writes) of adding first } n = 2 \text{ elements}</code-block><br/>
<step><code-block lang="tex"> \text{will ignore the cost of allocating/de-allocating arrays}</code-block><br/></step>
</procedure>

<table>
<tr>
<td>

<table>
<tr>
<th><code-block lang="tex"> n</code-block></th>
<th><code-block lang="tex"> append</code-block></th>
<th><code-block lang="tex"> copy</code-block></th>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td></td>
<td></td>
<td></td>
</tr>
</table>

</td>
<td>
<note>
<code-block lang="tex"> \text{Each row indicates the number of reads and writes} </code-block><br/>
<code-block lang="tex"> \text{necessary for appending an element into }  </code-block><br/>
<code-block lang="tex"> \text{an existing array of length } n </code-block>
</note>
<br/><br/>
<code-block lang="tex">
\begin{align*}
n + \sum_{i = 0}^{n - 1} i^2 &amp;= n + n^2 - n \\
\\
&amp;\Theta(n^2) \\
\end{align*}
</code-block>
<br/><br/>
<tip>
Think ,<a href="https://youtu.be/L3PMWMKI0YU">arithmetic sequences</a> and <a href="https://youtu.be/7Weu-TwS-S0">arithmetic series</a>
</tip>

</td>
</tr>
</table>

</tab>
<tab title="Doubling array">

<table>
<tr>
<td>
<img thumbnail="true" src="https://cdn-images-1.medium.com/max/960/1*9s7_mGUIzA_JcOOw-zQh9Q.png" alt="img" />
<br/><br/>
</td>
<td>
<note>
<code-block lang="tex"> \text{Each row indicates the number of reads and writes} </code-block><br/>
<code-block lang="tex"> \text{necessary for appending an element into }  </code-block><br/>
<code-block lang="tex"> \text{an existing array of length } n </code-block>
</note>
<br/><br/>
<code-block lang="tex">
\begin{align*}
n + \sum_{i = 1}^{log\ n} 2^i &amp;= n + 2^{log\ n + 1} - 1 \\
\\
&amp;\Theta(n) \\
\\
\sum^{n}_{i = 0} c^i &amp;= \frac{c^{n^2 + 1} - 1}{c - 1} \\
\end{align*}
</code-block>
<br/><br/>
<tip>
Think ,<a href="https://youtu.be/2M9LtyHnbnk">geometric sequences</a> and <a href="https://youtu.be/NS-2CpFuW9Q">geometric series</a>
</tip>

</td>
</tr>
</table>

</tab>
<tab title="Proof">
<procedure>
<img thumbnail="true" src="http://127.0.0.1:3000/courses/_build/html/_images/05_s20.png" alt="" />
</procedure>
</tab>
</tabs>

























