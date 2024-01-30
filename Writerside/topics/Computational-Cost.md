# Computational Cost

<show-structure for="chapter,procedure" depth="2"/>

<tabs>
    <tab title="Computational Complexity">
        <video src="https://youtu.be/YoZPTyGL2IQ?feature=shared" width="900" mini-player="true"/>
    </tab>
    <tab title="Space Complexity">
        <video src="https://youtu.be/yOb0BL-84h8?feature=shared" width="900" mini-player="true"/>
    </tab>
    <tab title="Algorithms Explained">
        <video src="https://youtu.be/47GRtdHOKMg?feature=shared" width="900" mini-player="true"/>
    </tab>
</tabs>

<table>
<tr>
<td>
<procedure>
<b>Empirical Model</b>
<step><format color="Gray">Run algorithms</format></step>
<step><format color="Gray">Measure actual runtime</format></step>
</procedure>
</td>
<td>
<procedure>
<b>Mathematical Model</b>
<step><format color="Orange" style="bold">Analyze</format> Operations</step>
<step><format color="GreenYellow"  style="bold">Develop</format> Model</step>
</procedure>
</td>
</tr>
</table>



## Theoretical Models

<table>
<tr>
<td>
<b>Mathematical Model</b>

- High-level analysis
    - <b class="brown">no need to implement</b>
- Independent of hardware / software
- Based on **counts** of basic <b class="brown">instructions</b>
    - additions, multiplications, comparisons,etc
    - exact definition <u>not important</u> but <b class="brown">must be relevant</b> to the problem
</td>
<td>
<b>Basic assumptions</b>

- In order to use a **formal framework**, we will make  certain assumptions
    - count basic instructions: additions, multiplications, comparisons, assignments
    - each instruction takes one time unit
    - instructions are executed sequentially
    - infinite memory
- Focus on <span class="green">analyzing <b>running time</b></u>
</td>
</tr>
</table>

### Some Rules of Analysis

<procedure>


<procedure>
<b>Single loops</b>
<step>essentially, <code-block lang="tex"> total\ iterations\ \times \bigg( \frac{total\ instructions\ performed\ }{ iteration} \bigg)</code-block></step>
</procedure>

<procedure style="choices">
<b>Nested loops</b>
<step>count instructions inside out</step>
<step>careful with the range of the loop</step>
<step>when possible, multiplications can be used for counts from each loop</step>
</procedure>

<procedure>
<b>Consecutive statements</b>
<step>just add the counts</step>
</procedure>

<procedure>
<b>Conditionals</b>
<step>consider the branch with the highest count</step>
</procedure>

</procedure>



### Examples

<deflist >
<def title="model">

What to count?
- only relevant instructions?
- all instructions?

```c++
for (int i = 0; i < n; i++) {
    std::cout << (2 * i);
}
```

<note>
<b>Application</b>
<code-block lang="tex"> \text{This code has a time complexity of } O(n). \text{ This is because the loop runs}</code-block>
<code-block lang="tex"> n \text{ times and the body of the loop has a time complexity of } O(1).</code-block>

```c++
#include <iostream>
using namespace std;

int main()
{
  int i, n = 8;
  for (i = 1; i <= n; i++) {
    cout << "Hello World !!!\n";
  }
  return 0;
}
```

<b>Output</b>

```text
Hello World !!!
Hello World !!!
Hello World !!!
Hello World !!!
Hello World !!!
Hello World !!!
Hello World !!!
Hello World !!!
```

</note>

<b>Time Complexity</b>
<code-block lang="tex"> \text{In the above code “Hello World !!!” is printed only } n \text{ times on the screen,}</code-block>
<code-block lang="tex"> \text{as the value of } n \text{ can change. So, the time complexity is linear: } O(n)</code-block>
<code-block lang="tex"> \text{ i.e. every time, a linear amount of time is required to execute code.}</code-block>

<b>Auxiliary Space</b>
<code-block lang="tex"> \text{The space complexity of the above code is constant: } O(1)</code-block>


</def>
<def title="x1" default-state="collapsed">

```c++
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        std::cout << (i * j);
    }
}
```

<procedure title="T(n) = ??" collapsible="true">
<note>
<code-block lang="tex"> \text{This code has a time complexity of } O(n^2).</code-block>
<code-block lang="tex"> \text{This is because it has nested loops that are both iterating over}</code-block>
<code-block lang="tex"> n\ \text{elements, so the total number of operations increases}</code-block>
<code-block lang="tex"> \text{quadratically with the size of the input.}</code-block>

</note>
</procedure>
</def>
<def title="x2">

```c++
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n * n; j++) {
        std::cout << (i * j);
    }
}
```

<procedure title="T(n) = ??" collapsible="true">
<note>
<code-block lang="tex"> \text{This code has a time complexity of } O(n^3).</code-block>
<code-block lang="tex"> \text{This is because there are two nested for loops, }</code-block>
<code-block lang="tex"> \text{the outer loop has a time complexity of } O(n),</code-block>
<code-block lang="tex"> \text{and the inner loop has a time complexity of } O(n^2),</code-block>
<code-block lang="tex"> \text{resulting in a time complexity of } O(n^3).</code-block>
<code-block lang="tex"> \text{The total time complexity is } O(n^3),</code-block>
<code-block lang="tex"> \text{because the inner loop is iterating } n * n \text{ times.}</code-block>
</note>
</procedure>

</def>
<def title="x3">

```c++
for (int i = 0; i < n; i++) {
    for (int j = 0; j < i; j++) {
        sum = sum * j;
    }
}
```

<procedure title="T(n) = ??" collapsible="true">
<note>
<code-block lang="tex"> \text{This code has a time complexity of } O(n^2). \text{ This is because }</code-block>
<code-block lang="tex"> \text{there is an outer loop that runs } n\ \text{times and an inner loop}</code-block>
<code-block lang="tex"> \text{that runs } i\ \text{times where } i\ \text{is the value of the outer loop’s iterator.}</code-block>
<code-block lang="tex"> \text{Since } i\ \text{starts at 0 and increases each iteration of the loop,}</code-block>
<code-block lang="tex"> \text{the inner loop will run 0 times on the first }</code-block>
</note>
</procedure>

</def>
<def title="x4">

```c++
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        for (int k = 0; k < n; k++) {
            //count 1 instruction
        }
    }
}
```

<procedure title="T(n) = ??" collapsible="true">
<note>
<code-block lang="tex"> \text{This code has a time complexity of } O(n^3) \text{ because }</code-block>
<code-block lang="tex"> \text{there are three nested loops, each of which runs } n\ \text{times.}</code-block>
<code-block lang="tex"> \text{The total number of operations is } n * n * n = n^3.</code-block>
</note>
</procedure>

</def>
<def title="x5">

```c++
for (int i = 0; i < n; i++) {
    for (int j = 0; j < i * i; j++) {
        for (int k = 0; k < j; k++) {
            // count 1 instruction
        }
    }
}
```

<procedure title="T(n) = ??" collapsible="true">
<note>
<code-block lang="tex"> \text{This code has a time complexity of } O(n^4). \text{ This is because }</code-block>
<code-block lang="tex"> \text{the first loop runs in } O(n) \text{ time, the second loop runs in } O(n^2)</code-block>
<code-block lang="tex"> \text{time, and the third loop runs in } O(n^3) \text{ time.}</code-block>
<code-block lang="tex"> \text{Therefore, the total time complexity is the product of all of these which is } O(n^4).</code-block>
</note>
</procedure>

</def>
</deflist>



## Understanding Cost

<procedure style="choices">
<p>Number of <format color="LightCoral">basic instructions</format> required by the algorithm to process an input of a certain size <code>n</code></p>
<code-block lang="tex"> T(n)</code-block>
<step>ex: find max in an array <code-block lang="tex"> \#  \ of\ comparisons</code-block></step>
<step>ex: sum elements in an array <code-block lang="tex"> \#  \ of\ additions</code-block></step>
</procedure>

### Cost Comparison

<table title="Cost">
<tr>
<th></th>
<th><code-block lang="tex"> 1d\ array</code-block><br/><code-block lang="tex"> find\ x = k</code-block></th>
<th><code-block lang="tex"> 2d\ array</code-block><br/><code-block lang="tex"> find (x,y)s.t. x + y = k</code-block></th>
<th><code-block lang="tex"> 3d\ array</code-block><br/><code-block lang="tex"> find (x,y,z)s.t. x + y + z = k</code-block></th>
</tr>
<tr>
<td><code-block lang="tex"> input\ size</code-block></td>
<td><code-block lang="tex"> n</code-block></td>
<td><code-block lang="tex"> n^2</code-block></td>
<td><code-block lang="tex"> n^3</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 1</code-block></td>
<td><code-block lang="tex"> 1</code-block></td>
<td><code-block lang="tex"> 1</code-block></td>
<td><code-block lang="tex"> 1</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 10</code-block></td>
<td><code-block lang="tex"> 10</code-block></td>
<td><code-block lang="tex"> 100</code-block></td>
<td><code-block lang="tex"> 1000</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 100</code-block></td>
<td><code-block lang="tex"> 100</code-block></td>
<td><code-block lang="tex"> 10000</code-block></td>
<td><code-block lang="tex"> 1000000</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 1000</code-block></td>
<td><code-block lang="tex"> 1000</code-block></td>
<td><code-block lang="tex"> 1000000</code-block></td>
<td><code-block lang="tex"> 1000000000</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 10000</code-block></td>
<td><code-block lang="tex"> 10000</code-block></td>
<td><code-block lang="tex"> 100000000</code-block></td>
<td><code-block lang="tex"> 1000000000000</code-block></td>
</tr>
</table>


### Growth Rate

<table>
<tr>
<th><code-block lang="tex"> Constant</code-block></th>
<th><code-block lang="tex"> Logarithmic</code-block></th>
<th><code-block lang="tex"> Linear</code-block></th>
<th><code-block lang="tex"> Linearithemic</code-block></th>
<th><code-block lang="tex"> Polynomial</code-block><br/><code-block lang="tex">(Quadratic)</code-block></th>
<th><code-block lang="tex"> Exponential</code-block></th>
<th><code-block lang="tex"> Factorial</code-block></th>
</tr>
<tr>
<td><code-block lang="tex"> 1</code-block></td>
<td><code-block lang="tex"> log\ n</code-block></td>
<td><code-block lang="tex"> n</code-block></td>
<td><code-block lang="tex"> n\ log\ n</code-block></td>
<td><code-block lang="tex"> n^2</code-block></td>
<td><code-block lang="tex"> 2^n</code-block></td>
<td><code-block lang="tex"> n!</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 16</code-block></td>
<td><code-block lang="tex"> 4</code-block></td>
<td><code-block lang="tex"> 2^4</code-block></td>
<td><code-block lang="tex"> 64</code-block></td>
<td><code-block lang="tex"> 256</code-block></td>
<td><code-block lang="tex"> 65536</code-block></td>
<td><code-block lang="tex"> 20922789888000</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 256</code-block></td>
<td><code-block lang="tex"> 8</code-block></td>
<td><code-block lang="tex"> 2^8</code-block></td>
<td><code-block lang="tex"> 2048</code-block></td>
<td><code-block lang="tex"> 65536</code-block></td>
<td><code-block lang="tex"> 1.1579209e+77</code-block></td>
<td><code-block lang="tex"> 4.0329146e+38</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 1024</code-block></td>
<td><code-block lang="tex"> 10</code-block></td>
<td><code-block lang="tex"> 2^{10}</code-block></td>
<td><code-block lang="tex"> 10240</code-block></td>
<td><code-block lang="tex"> 1048576</code-block></td>
<td><code-block lang="tex"> 1.0715086e+308</code-block></td>
<td><code-block lang="tex"> 2.5563239e+256</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 65K</code-block></td>
<td><code-block lang="tex"> 16</code-block></td>
<td><code-block lang="tex"> 2^{16}</code-block></td>
<td><code-block lang="tex"> 1M</code-block></td>
<td><code-block lang="tex"> 4.3B</code-block></td>
<td><code-block lang="tex"> 3.68935e+197</code-block></td>
<td><code-block lang="tex"> 1.26887e+197</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 1M</code-block></td> 
<td><code-block lang="tex"> 20</code-block></td>
<td><code-block lang="tex"> 2^{20}</code-block></td>
<td><code-block lang="tex"> 20M</code-block></td>
<td><code-block lang="tex"> 1T</code-block></td>
<td><code-block lang="tex"> 1.26765e+301</code-block></td>
<td><code-block lang="tex"> 8.26393e+294</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 1G</code-block></td>
<td><code-block lang="tex"> 30</code-block></td>
<td><code-block lang="tex"> 2^{30}</code-block></td>
<td><code-block lang="tex"> 30G</code-block></td>
<td><code-block lang="tex"> 1P</code-block></td>
<td><code-block lang="tex"> 1.07374e+301</code-block></td>
<td><code-block lang="tex"> 1.08889e+308</code-block></td>
</tr>
</table>


































