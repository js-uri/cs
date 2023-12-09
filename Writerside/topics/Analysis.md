---
Reorder the asymptotic bounds throughout the page
---

# Analysis of Algorithms

![hero](https://i.ytimg.com/vi/bxgTDN9c6rg/maxresdefault.jpg)



## Basic Algorithmic Analysis

<deflist collapsible="true" default-state="collapsed">
<def title="Objectives">

- Understand the basics of algorithmic efficiency, including time and space complexity.
- Learn to analyze algorithms in terms of their worst-case, average-case, and best-case scenarios.

</def>
</deflist>



### Time Complexity

<note>
<p>a measure of the amount of time an algorithm takes to complete as a function of the input size. It helps us understand how the algorithm's execution time increases with the size of the input.</p>
</note>

<table>
<tr>
<td>
<b><code-block lang="tex"> Big-O\ Notation\ O(?) \\ \\</code-block></b><br/>
<img src="https://1.bp.blogspot.com/-F005AXl7vvQ/XPhoLqUPwFI/AAAAAAAAByg/AqTtz6olGvYLUHoHwE8oXL3mstzwuqIsQCLcBGAs/s400/BigO.png" alt="image"/><br/>
<p>Describes the upper bound or worst-case time complexity of an algorithm. It provides an asymptotic upper limit on 
the growth rate of the function.</p>
</td>
<td>
<b><code-block lang="tex"> Big-Omega\ Notation\ \Omega(?) \\ \\</code-block></b>
<br/>
<img src="https://1.bp.blogspot.com/-N5zwyl8TFYc/XPho3ALZOHI/AAAAAAAAByo/3JgCK6FrPq0eAJuR_xL_P-P9RGmVg91WQCLcBGAs/s400/BigOmega.png" alt="image"/><br/>
<p>Represents the lower bound or best-case time complexity of an algorithm. It provides an asymptotic lower limit on the growth rate of the function.</p>
</td>
<td>
<b><code-block lang="tex"> Theta\ Notation\ \Theta(?) \\ \\</code-block></b><br/>
<img src="https://1.bp.blogspot.com/-sOrn-Gb-TtU/XPhqa31EyHI/AAAAAAAABy0/GOTyvRcbKQAe4F2zY6VqDl60gt-9AM1ogCLcBGAs/s400/BigTheta.png" alt="image"/><br/>
<p>Specifies both upper and lower bounds, indicating that the algorithm's running time is tightly bound within these limits.</p>
</td>
</tr>
</table>

#### Algorithmic Counting { collapsible="true" default-state="collapsed" }

<table>
<tr>
<td><img src="https://dz2cdn1.dzone.com/storage/temp/13847345-1597432212084.png" alt="" /></td>
<td><img src="https://dz2cdn1.dzone.com/storage/temp/13847344-1597432202813.png" alt="" /></td>
</tr>
</table>

### Space Complexity

<note>
<p>refers to the amount of memory an algorithm requires in relation to the input size.</p>
</note>

<table>
<tr>
<td>
<b><p>Auxiliary Space Complexity</p></b><br/>
<img src="https://storage.googleapis.com/algodailyrandomassets/curriculum/fundamentals/space1.png" alt="image"/><br/>
<p>Describes the extra space used by the algorithm, excluding the input space.</p>
</td>
<td>
<b><p>In-place Algorithms</p></b><br/>
<img src="https://2.bp.blogspot.com/-g3oiQPwQhAc/Wrc_OBwnA2I/AAAAAAAAB3U/EwcqWSh42lIekbeeVGk9J7IuNECZ0MLqwCLcBGAs/s1600/inplace.tif" alt="image"/><br/>
<p>Algorithms that use a constant amount of extra space, making them memory-efficient.</p>
</td>
</tr>
</table>



## Analyzing Cases

<table >
<tr>
<td>
<procedure>
<b>Worst-case Scenario</b>
<step>represents the maximum amount of time an algorithm takes for any input size. It is important for ensuring that the algorithm performs well in all situations.</step>
</procedure>

<procedure>
<b>Identifying Worst Cases</b>
<step>Determine the input conditions that lead to the highest time complexity.</step>
</procedure>

<procedure>
<code-block lang="tex"> Big-O\ Notation\ O(?)</code-block><br/>
<step>Often used to express the worst-case time complexity.</step>
</procedure>
</td>

<td>
<procedure>
<b>Average-Case Scenario</b>
<step>provides a measure of the expected performance of an algorithm when considering all possible inputs.<br/></step>
</procedure>

<procedure>
<b>Statistical Analysis</b>
<step>Requires knowledge of the probability distribution of inputs.<br/></step>
</procedure>

<procedure>
<code-block lang="tex"> Theta\ Notation\ \Theta(?) \\ \\</code-block><br/>
<step>Often used to express the average-case time complexity.</step>
</procedure>

</td>
<td>
<procedure>
<b>Best-Case Scenario</b>
<step>represents the minimum amount of time an algorithm takes for a particular input size. It is useful for understanding the algorithm's optimal performance.</step>
</procedure>

<procedure>
<b>Identifying Best Cases</b>
<step>Determine the input conditions that lead to the lowest time complexity.<br/></step>
</procedure>

<procedure>
<code-block lang="tex"> Big-Omega\ Notation\ \Omega(?)</code-block><br/>
<step>Often used to express the best-case time complexity.<br/></step>
</procedure>

</td>
</tr>
</table>




















