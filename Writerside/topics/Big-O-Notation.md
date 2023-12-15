# Big-O Notation

<video src="https://youtu.be/__vX2sjlpXU?feature=shared" width="900" mini-player="true"/>

## The story so far...

<table>
<tr>
<td width="50%">
Can measure actual runtime to compare algorithms

- however, runtime is noisy (highly sensitive to hardware/software and implementation details)
</td>
<td>
Can count instructions to compare algorithms

- can define <code-block lang="tex"> T(n)</code-block> which depends on the input size
- for large inputs, our focus should be on the dominant terms of <code-block lang="tex"> T(n)</code-block>

</td>
</tr>
</table>



## Inline Math

<procedure style="choices">
<b>Sequence</b>
<note>also known as a progression, is a successive arrangement of numbers in an order according to some specific rules</note>
<p>Depending upon the number of terms in a sequence, it is classified into two types, namely a finite sequence and an infinite sequence.</p>
<code-block lang="tex"> \text{ Examples}</code-block>
<step><code-block lang="tex"> \text{ finite arithmetic sequence : 
} 3, 5, 7, 9, 11</code-block></step>
<step><code-block lang="tex"> \text{ infinite arithmetic sequence : 
} 3, 5, 7, 9, 11, \dots </code-block></step>
</procedure>

<procedure style="choices">
<b>Series</b>
<note>formed by <i>adding</i> the elements of a sequence</note>
<p>Depending on whether the sequence is finite or infinite, the series can be either finite or infinite.</p>
<code-block lang="tex"> \text{ Examples}</code-block>
<step><code-block lang="tex"> \text{ finite arithmetic sequence : 
} 3 + 5 + 7 + 9 + 11</code-block></step>
<step><code-block lang="tex"> \text{ infinite arithmetic sequence : 
} 3 + 5 + 7 + 9 + 11 + \dots </code-block></step>
</procedure>



## Comparing Algorithms

<procedure title="Comparative Rules">
<step><code-block lang="tex"> log\ ab = log\ a + log\ b \\</code-block></step>
<step><code-block lang="tex"> log\ \frac{a}{b} = log\ a - log\ b \\</code-block></step>
<step><code-block lang="tex"> log\ a^b = b\ log\ a \\</code-block></step>
<step><code-block lang="tex"> a^{log^{b}_{c}} = b^{log^{a}_{c}} \\</code-block></step>
<step><code-block lang="tex"> a^b = n \Rightarrow b = log_a\ n \\</code-block></step>
</procedure>

<deflist collapsible="true" default-state="collapsed">
<def title="Compare two...">

<procedure style="choices">
<p>Are these the same?</p>
<step><format color="GreenYellow"><code-block lang="tex"> T(n) = 2n</code-block></format></step>
<step><format color="Orange"><code-block lang="tex"> T(n) = 25n</code-block></format></step>
</procedure>

<table>
<tr>

[//]: # (TODO : ADD IMAGES)
<td><img src="https://placehold.co/600x400" alt="" /></td>
<td><img src="https://placehold.co/600x400" alt="" /></td>
</tr>
</table>
</def>
<def title="Compare three...">

<procedure style="choices">
<p>Are these the same?</p>
<step><format color="GreenYellow"><code-block lang="tex"> T(n) = 2n</code-block></format></step>
<step><format color="Orange"><code-block lang="tex"> T(n) = 25n</code-block></format></step>
<step><format color="DodgerBlue"><code-block lang="tex"> T(n) = n^2</code-block></format></step>
</procedure>

<table>
<tr>

[//]: # (TODO : ADD IMAGES)
<td><img src="https://placehold.co/600x400" alt="" /></td>
<td><img src="https://placehold.co/600x400" alt="" /></td>
<td><img src="https://placehold.co/600x400" alt="" /></td>
</tr>
</table>
</def>
<def title="Compare two more...">

<procedure style="choices">
<p>Are these the same?</p>
<step><format color="GreenYellow"><code-block lang="tex"> T(n) = 1000n + 500</code-block></format></step>
<step><format color="Orange"><code-block lang="tex"> T(n) = n^2</code-block></format></step>
</procedure>

<table>
<tr>

[//]: # (TODO : ADD IMAGES)
<td><img src="https://placehold.co/600x400" alt="" /></td>
<td><img src="https://placehold.co/600x400" alt="" /></td>
</tr>
<tr>

[//]: # (TODO : ADD IMAGES)
<td><img src="https://placehold.co/600x400" alt="" /></td>
<td><img src="https://placehold.co/600x400" alt="" /></td>
</tr>
</table>
</def>
<def title="Bottomline...">

<procedure style="choices">
<code-block lang="tex"> \text{Trying to compare } T(n) \text{ functions, but...}</code-block>
<step><code-block lang="tex"> \text{we need to about large values of } n</code-block></step>
</procedure>

<procedure style="choices">
<code-block lang="tex"> \text{Can we properly define } &le; \text{ for functions?}</code-block>
<step><code-block lang="tex"> \text{we can group functions into } sets \text{ and make our lives easier}</code-block></step>
</procedure>
</def>
</deflist>



## Asymptotic Analysis

<note>refers to the study of an algorithm as the input size “gets big” or reaches a limit (in the calculus sense)</note>

### Growth Rate

<note>rate at which the cost of an algorithm grows as the size of its input grows</note>

### Common Sets of Functions

<table>
<tr>
<td>
<img src="http://127.0.0.1:3000/courses/_build/html/_images/04_s11.png" alt="" />
</td>
<td>
<procedure style="choices">
<code-block lang="tex"> \text{Algorithm } A \text{ is better than Algorithm } B \text{ if…}</code-block>
<step><code-block lang="tex"> \text{for large values of } n, T_A(n) \text{ grows slower than } T_B(n)</code-block></step>
<step><code-block lang="tex"> \text{Note: Faster growth rate…slower algorithm…}</code-block></step>
</procedure>
</td>
</tr>
</table>

### Examples

[//]: # (<table>)











[//]: # (</table>)

<table>
<tr>
<td>order of growth</td>
<td>name</td>
<td>typical code framework</td>
<td>description</td>
<td>example</td>
</tr>
<tr>
<td><code-block lang="tex"> 1</code-block></td>
<td>constant</td>
<td><code-block lang="c++">a = b + c;</code-block></td>
<td>statement</td>
<td>add two numbers</td>
</tr>
<tr>
<td><code-block lang="tex"> log\ n</code-block></td>
<td>logarithmic</td>
<td>

```c++
while (n > 1) {
  /*do something*/
}
```
</td>
<td>divide in half</td>
<td>binary search</td>
</tr>
<tr>
<td><code-block lang="tex"> n</code-block></td>
<td>linear</td>
<td>

```c++
for (int i = 0; i < n; i++) {
  /*do something*/
}
```
</td>
<td>single loop</td>
<td>find the maximum</td>
</tr>
<tr>
<td><code-block lang="tex"> n\ log\ n</code-block></td>
<td>linearithmic</td>
<td><code-block lang="tex">
// \ see\ mergesort
</code-block></td>
<td>divide &amp; conquer</td>
<td>mergesort</td>
</tr>
<tr>
<td><code-block lang="tex"> n^2</code-block></td>
<td>polynomial<br/>(quadratic)</td>
<td>

```c++
for (int i = 0; i < n; i++) {
  for (int j = 0; j < n; j++) { 
    /*do something*/
  }
}
```
</td>
<td>double loop</td>
<td>check all pairs</td>
</tr>
<tr>
<td><code-block lang="tex"> n^3</code-block></td>
<td>polynomial</td>
<td>

```c++ 
for (int i = 0; i < n; i++) {
  for (int j = 0; j < n; j++) {
    for (int k = 0; k < n; k++) { 
      /*do something*/
    }
  }
}
```

</td>
<td>double loop</td>
<td>check all pairs</td>
</tr>
<tr>
<td><code-block lang="tex"> 2^n</code-block></td>
<td>exponential</td>
<td><code-block lang="tex">
// \ see\ combinatorial\ search
</code-block></td>
<td>exhaustive search</td>
<td>check all subsets</td>
</tr>
</table>


### Asymptotic Bounds

<procedure>
<tabs>

<tab title="Defined">
<img src="https://placehold.co/600x400" alt="" />
<br/><br/>
<p>Asymptotic bounds are a way of describing the behavior of an algorithm as the input size approaches infinity. They are used to analyze the time and space complexity of algorithms, and are expressed in terms of upper and lower bounds.</p>
<p>The most commonly used asymptotic bounds are Big-O notation, Omega notation, and Theta notation.</p>
<br/>
<procedure>
<b>Big-O notation</b>
<p>is an upper bound on the growth rate of an algorithm. It describes the worst-case scenario of an algorithm’s time complexity.</p>
<step>

```tex
\text{if an algorithm has a time complexity of } O(n^2) \text{ means that the running}
```
```tex
\text{time of the algorithm grows no faster than } n^2 
```
</step>
</procedure>
<procedure>
<b>Big-Omega notation</b>
<p>is a lower bound on the growth rate of an algorithm. It describes the best-case scenario of an algorithm’s time complexity.</p>
<step>

```tex
\text{if an algorithm has a time complexity of } \Omega(n^2) \text{ means that the running}
```
```tex
\text{time of the algorithm grows at least as fast as } n^2 
```
</step>
</procedure>
<procedure>
<b>Theta notation</b>
<p>provides both an upper and lower bound on the growth rate of an algorithm. It describes the tight bound on the growth rate of an algorithm.</p>
<step>

```tex
\text{if an algorithm has a time complexity of } \Theta(n^2) \text{ means that the running}
```
```tex
\text{time of the algorithm grows exactly as fast as } n^2 
```
</step>
</procedure>
<br/>
<p>Asymptotic bounds are useful because they allow us to compare the efficiency of different algorithms and to choose the most appropriate one for a given task.</p>
</tab>

<tab title="Big-O">
<note>
<p>Definition</p>
<img src="http://127.0.0.1:3000/courses/_build/html/_images/04_s13.png" alt=""/>
<br/><br/>
<procedure>
<p>Translation</p>
<code-block lang="tex">
T(n) \text{ is upper bounded by } f(n) \text{ if and only if } T(n) \text{ is less than or} \\
</code-block>
<code-block lang="tex"> 
\text{ equal to some constant } C \times f(n) \text{ the function we chose to bound with} \\</code-block>
<code-block lang="tex">
\text{for all } N \text{ greater than the initial } n \text{ or not}
</code-block>
</procedure>
<procedure>
<p>Examples</p>
<code-block lang="tex">
\begin{align*}
c.g : f(n) &= 2n + 3 \\
2n + 3 &amp; \le \ ?? \\
2n + 3 &amp; \le 10n \Rightarrow O(n) \\
&amp; \text{alternatively} \\
2n + 3 &amp; \le 5n^2 \Rightarrow O(n^2) \\
\end{align*}
</code-block>
</procedure>
</note>
</tab>

<tab title="Big-Omega">
<note>
<p>Definition</p>
<img src="http://127.0.0.1:3000/courses/_build/html/_images/04_s15.png" alt=""/>
<br/><br/>
<procedure>
<p>Translation</p>
<code-block lang="tex">
T(n) \text{ is lower bounded by } f(n) \text{ if and only if } T(n) \text{ is greater than or} \\
</code-block>
<code-block lang="tex"> 
\text{ equal to some constant } C \times f(n) \text{ the function we chose to bound with} \\</code-block>
<code-block lang="tex">
\text{for all } N \text{ less than the initial } n \text{ or not}
</code-block>
</procedure>
<procedure>
<p>Examples</p>
<code-block lang="tex">
\begin{align*}
c.g : f(n) &= 2n + 3 \\
2n + 3 &amp;\le 1 * n\ \forall n \le 1 \\
2n + 3 &amp;\le n \Rightarrow \Omega(n) \\
&amp;\text{alternatively} \\
2n + 3 &amp;\le 1 * log\ n\ \forall n \le 1 \\
2n + 3 &amp;\le 1 * log\ n\ \Rightarrow \Omega(log\ n) \\
\end{align*}
</code-block>
</procedure>
</note>
</tab>

<tab title="Theta">
<note>
<p>Definition</p>
<img src="http://127.0.0.1:3000/courses/_build/html/_images/04_s16.png" alt=""/>
<br/><br/>
<procedure>
<p>Translation</p>
<code-block lang="tex">
[//]: # (TODO : FIX THIS EQUATION)
T(n) \text{ is lower bounded by } f(n) \text{ if and only if } T(n) \text{ is equal to some constant} \\
</code-block>
<code-block lang="tex"> 
\text{  } C \times f(n) \text{ the function we chose to bound with} \\</code-block>
<code-block lang="tex">
\text{for all } N \text{ less than the initial } n \text{ or not}
</code-block>
</procedure>
<procedure>
<p>Examples</p>
<code-block lang="tex">
\begin{align*}
c.g : f(n) &amp;= 2n + 3 \\
Big-\Omega &amp;\le 2n + 3 &amp;\le Big-O \\
1 * n\ &amp;\le 2n + 3 &amp;\le 5 * n \Rightarrow \Theta(n) \\
\end{align*}
</code-block>
</procedure>
</note>
</tab>
</tabs>
</procedure>

<tip>In practice, ignore constants and drop lower order terms...</tip>


### Advantages &amp; Disadvantages

<table>
<tr>
<th>
<procedure style="choices">
<p>✅</p>
<step>Asymptotic analysis provides a high-level understanding of how an algorithm performs with respect to input size.</step>
<step>It is a useful tool for comparing the efficiency of different algorithms and selecting the best one for a specific problem.</step>
<step>It helps in predicting how an algorithm will perform on larger input sizes, which is essential for real-world applications.</step>
<step>Asymptotic analysis is relatively easy to perform and requires only basic mathematical skills.</step>
</procedure>
</th>
<th>
<procedure style="choices">
<p>❌</p>
<step>Asymptotic analysis does not provide an accurate running time or space usage of an algorithm.</step>
<step>It assumes that the input size is the only factor that affects an algorithm’s performance, which is not always the case in practice.</step>
<step>Asymptotic analysis can sometimes be misleading, as two algorithms with the same asymptotic complexity may have different actual running times or space usage.</step>
<step>It is not always straightforward to determine the best asymptotic complexity for an algorithm, as there may be trade-offs between time and space complexity.</step>
</procedure>
</th>
</tr>
</table>

### True or False

<tip>

```tex
\text{time complexity growth rates : } 1 , log\ n , n , n\ log\ n , n^2 , n^3 , 2^n , n! 
```
</tip>

<tabs>
<tab title="Test yourself...">
<table>
<tr>
<th></th><th><code-block lang="tex"> \text{Big-O}</code-block></th><th><code-block lang="tex"> \text{Big-}\Omega</code-block></th><th><code-block lang="tex"> \Theta</code-block></th>
</tr>
<tr>
<td><code-block lang="tex"> 10^2 + 3000n + 10</code-block></td><td></td><td></td><td></td>
</tr>
<tr>
<td><code-block lang="tex"> 21\ log\ n</code-block></td><td></td><td></td><td></td>
</tr>
<tr>
<td><code-block lang="tex"> 500\ log\ n + n^4</code-block></td><td></td><td></td><td></td>
</tr>
<tr>
<td><code-block lang="tex"> \sqrt{n} + log\ n^{50}</code-block></td><td></td><td></td><td></td>
</tr>
<tr>
<td><code-block lang="tex"> 4^n + n^{5000}</code-block></td><td></td><td></td><td></td>
</tr>
<tr>
<td><code-block lang="tex"> 3000n^3 + n^{3.5}</code-block></td><td></td><td></td><td></td>
</tr>
<tr>
<td><code-block lang="tex"> 2^5 + n!</code-block></td><td></td><td></td><td></td>
</tr>
</table>
</tab>
<tab title="Answers...">
<table>
<tr>
<th></th><th><code-block lang="tex"> \text{Big-O}</code-block></th><th><code-block lang="tex"> \text{Big-}\Omega</code-block></th><th><code-block lang="tex"> \Theta</code-block></th>
</tr>
<tr>
<td><code-block lang="tex"> 10^2 + 3000n + 10</code-block></td>
<td><code-block lang="tex"> n</code-block></td>
<td><code-block lang="tex"> n</code-block></td>
<td><code-block lang="tex"> \text{true}</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 21\ log\ n</code-block></td>
<td><code-block lang="tex"> log\ n</code-block></td>
<td><code-block lang="tex"> log\ n</code-block></td>
<td><code-block lang="tex"> \text{true}</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 500\ log\ n + n^4</code-block></td>
<td><code-block lang="tex"> n^2</code-block></td>
<td><code-block lang="tex"> log\ n</code-block></td>
<td><code-block lang="tex"> \text{false}</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> \sqrt{n} + log\ n^{50}</code-block></td>
<td><code-block lang="tex"> log\ n</code-block></td>
<td><code-block lang="tex"> log\ n</code-block></td>
<td><code-block lang="tex"> \text{true}</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 4^n + n^{5000}</code-block></td>
<td><code-block lang="tex"> 2^n</code-block></td>
<td><code-block lang="tex"> n^2</code-block></td>
<td><code-block lang="tex"> \text{false}</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 3000n^3 + n^{3.5}</code-block></td>
<td><code-block lang="tex"> n^2</code-block></td>
<td><code-block lang="tex"> n^2</code-block></td>
<td><code-block lang="tex"> \text{true}</code-block></td>
</tr>
<tr>
<td><code-block lang="tex"> 2^5 + n!</code-block></td>
<td><code-block lang="tex"> n!</code-block></td>
<td><code-block lang="tex"> n!</code-block></td>
<td><code-block lang="tex"> \text{true}</code-block></td>
</tr>
</table>
</tab>
</tabs>

<tip>
<procedure style="choices">
<p>Asymptotic Performance</p>
<step><code-block lang="tex"> \text{For large values of } n \text{ a } \Theta(n^2) \text{ algorithm always beats a } \Theta(n^3) \text{ algorithm}</code-block></step>
<step><i>However, we shouldn't completely ignore asymptotically slower algorithms</i></step>
</procedure>
</tip>




















