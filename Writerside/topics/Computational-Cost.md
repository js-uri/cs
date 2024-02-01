# Computational / Mathematical

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

<br/>

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

## Inline Math

<table>
<tr>
<td colspan="2">
<procedure style="choices">
<b>Sequence</b>
<note>also known as a progression, is a successive arrangement of numbers in an order according to some specific rules</note>
<p>Depending upon the number of terms in a sequence, it is classified into two types, namely a finite sequence and an infinite sequence.</p>
<code-block lang="tex"> \text{ Examples}</code-block>
<step><code-block lang="tex"> \text{ finite arithmetic sequence : } 3, 5, 7, 9, 11</code-block></step>
<step><code-block lang="tex"> \text{ infinite arithmetic sequence : } 3, 5, 7, 9, 11, \dots </code-block></step>
</procedure>
<br/>
<procedure style="choices">
<b>Series</b>
<note>formed by <i>adding</i> the elements of a sequence</note>
<p>Depending on whether the sequence is finite or infinite, the series can be either finite or infinite.</p>
<code-block lang="tex"> \text{ Examples}</code-block>
<step><code-block lang="tex"> \text{ finite arithmetic sequence : } 3 + 5 + 7 + 9 + 11</code-block></step>
<step><code-block lang="tex"> \text{ infinite arithmetic sequence : } 3 + 5 + 7 + 9 + 11 + \dots </code-block></step>
</procedure>

<procedure>
<b>Sigma Notation</b> <i>(example)</i>

![image](https://www.onlinemathlearning.com/image-files/sigma-notation.png)
{width="100"}

```tex
\sum_{i=1}^{n} i = 1 + 2 + 3 + \dots + n
```
</procedure>
</td>
</tr>
<tr>
<td>
<tip>
<p>Sigma Example 1</p>

[Walkthrough](https://opendsa-server.cs.vt.edu/embed/SummationOneToNCON)

</tip>
</td>
<td>
<tip>
<p>Sigma Example 2</p>

[Walkthrough](https://opendsa-server.cs.vt.edu/embed/SummationTwoPowerICON)

</tip>
</td>
</tr>
</table>


<procedure title="Formulas &amp; Proofs">
<tabs>
<tab title="Arithmetic">
<p>where each term of the sequence is formed either by adding or subtracting a common term from the preceding number</p><br/>

```tex
\begin{align}
\text{Series : } & \\
\\
& a, a+d, a+2d, a+3d, ... \\
\\
\\
\text{Formula : } & \\
\\
\sum_{i=1}^{n} i & = \frac{n(n+1)}{2} \\
\\
\sum_{i=1}^{n} i^2 & = \frac{n(n+1)(2n+1)}{6} \\
\\
\sum_{i=1}^{n} i^3 & = \frac{n^2(n+1)^2}{6} \\
\\
\text{Problem : } & \\
\\
& \text{Find the sum of the first 100 positive integers} \\
\\
\\
\text{Algorithm : } & \\
\\
& \text{int sum = 0;} \\
& \text{for (int i = 1; i <= 100; i++)} \\
& \text{\{} \\
& \text{ sum += i;} \\
& \text{\}} \\
\\
\\
\text{Proof : } & \\
\\
\sum_{i=1}^{100} i & = \frac{100(100+1)}{2} \\
& = 5050 \\
\end{align}
```

</tab>
<tab title="Geometric">
<p>where each term of the sequence is formed either by multiplying or dividing a common term with the preceding number</p><br/>

```tex
\begin{align}
\text{Series : } & \\
\\
& a, ar, ar^2, ar^3, ... \\
\\
\\
\text{Formula : } & \\
\\
\sum_{i=1}^{n} r^i & = \frac{r^{n+1} - 1}{r - 1} \\
\\
\\
\text{Problem : } & \\
\\
& \text{Find the sum of the first 10 terms of the geometric sequence 2, 4, 8, 16, ...} \\
\\
\\
\text{Algorithm : } & \\
\\
& \text{int sum = 0;} \\
& \text{for (int i = 1; i <= 10; i++)} \\
& \text{\{} \\
& \text{ sum += Math.pow(2, i);} \\
& \text{\}} \\
\\
\\
\text{Proof : } & \\
\\
\sum_{i=1}^{10} 2^i & = \frac{2^{10+1} - 1}{2 - 1} \\
& = 2047 \\
\end{align}
```

</tab>
<tab title="Harmonic">
<p>where each term of the sequence is an infinite series of the reciprocals of positive integers</p><br/>

```tex
\begin{align}
\text{Series : } & \\
\\
& 1, \frac{1}{2}, \frac{1}{3}, \frac{1}{4}, ... \\
\\
\\
\text{Formula : } & \\
\\  
\sum_{i=1}^{n} \frac{1}{i} & = \ln n + \gamma + \epsilon_n \\
\\
\\
\text{Problem : } \\
\\
& \text{Find the sum of the first 10 terms of the harmonic sequence}  \\
\\
\\
\text{Algorithm : } \\
\\
& \text{double sum = 0;} \\
& \text{for (int i = 1; i <= 10; i++)} \\
& \text{\{} \\
& \text{ sum += 1.0 / i;} \\
& \text{\}} \\
\\
\\
\text{Proof : } \\
\\
\sum_{i=1}^{10} \frac{1}{i} & = \ln 10 + \gamma + \epsilon_{10} \\
& \approx 2.9289682539682538 \\
\end{align}
```

</tab>
<tab title="Logarithmic">
<p>where each term of the sequence is the logarithm of the element of an arithmetic sequence</p><br/>

```tex
\begin{align}
\text{Series : } & \\
\\
& \log 1, \log 2, \log 3, \log 4, ... \\
\\
\\
\text{Formula : } & \\
\\
\sum_{i=1}^{n} \log i & = \log n! \\
\\
\\
\text{Problem : } \\
\\
& \text{Find the sum of the first 10 terms of the logarithmic sequence}  \\
\\
\\
\text{Algorithm : } \\
\\
& \text{double sum = 0;} \\
& \text{for (int i = 1; i <= 10; i++)} \\
& \text{\{} \\
& \text{ sum += Math.log(i);} \\
& \text{\}} \\
\\
\\
\text{Proof : } \\
\\
\sum_{i=1}^{10} \log i & = \log 10! \\
& \approx 15.104412573075518 \\
\end{align}
```

</tab>
<tab title="Factorial">
<p>where each term of the sequence is the factorial of the element of an arithmetic sequence</p><br/>

```tex
\begin{align}
\text{Series : } & \\
\\
& 1!, 2!, 3!, 4!, ... \\
\\
\\
\text{Formula : } & \\
\\
\sum_{i=1}^{n} i! & = (n+1)! - 1 \\
\\
\\
\text{Problem : } \\
\\
& \text{Find the sum of the first 10 terms of the factorial sequence}  \\
\\
\\
\text{Algorithm : } \\
\\
& \text{int sum = 0;} \\
& \text{for (int i = 1; i <= 10; i++)} \\
& \text{\{} \\
& \text{ sum += factorial(i);} \\
& \text{\}} \\
\\
\\
\text{Proof : } \\
\\
\sum_{i=1}^{10} i! & = (10+1)! - 1 \\
& = 362879 \\
\end{align}
```

</tab>
<tab title="Exponential">
<p>where each term of the sequence is the exponential of the element of an arithmetic sequence</p><br/>

```tex
\begin{align}
\text{Series : } & \\
\\
& e^1, e^2, e^3, e^4, ... \\
\\
\\
\text{Formula : } & \\
\\
\sum_{i=1}^{n} e^i & = \frac{e^{n+1} - 1}{e - 1} \\
\\
\\
\text{Problem : } \\
\\
& \text{Find the sum of the first 10 terms of the exponential sequence}  \\
\\
\\
\text{Algorithm : } \\
\\
& \text{double sum = 0;} \\
& \text{for (int i = 1; i <= 10; i++)} \\
& \text{\{} \\
& \text{ sum += Math.exp(i);} \\
& \text{\}} \\
\\
\\
\text{Proof : } \\
\\
\sum_{i=1}^{10} e^i & = \frac{e^{10+1} - 1}{e - 1} \\
& \approx 22025.465794806718 \\
\end{align}
```



</tab>
</tabs>
</procedure>


<procedure title="Comparative Rules">
<step><code-block lang="tex"> log\ ab = log\ a + log\ b \\</code-block></step>
<step><code-block lang="tex"> log\ \frac{a}{b} = log\ a - log\ b \\</code-block></step>
<step><code-block lang="tex"> log\ a^b = b\ log\ a \\</code-block></step>
<step><code-block lang="tex"> a^{log^{b}_{c}} = b^{log^{a}_{c}} \\</code-block></step>
<step><code-block lang="tex"> a^b = n \Rightarrow b = log_a\ n \\</code-block></step>
</procedure>
































