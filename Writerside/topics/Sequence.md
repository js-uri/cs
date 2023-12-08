# Sequences

<video src="https://youtu.be/dYfgSLGV3mc?feature=shared" mini-player="false"/>

<note>
<p>a function whose domain is the set of *positive* integers:</p>
<p>
<code-block lang="tex">
\begin{align}
\{ 1, 2, 3, 4, \dots \}
\end{align}
</code-block>
</p>

</note>



<table>
<tr><td colspan="8"><p>The general, or <code-block lang="tex">\n^{th}</code-block> term, is denoted as <code-block 
lang="tex">\a_{n}
</code-block></p></td></tr>
<tr>
<td>odd integers</td>
<td>1</td>
<td>3</td>
<td>5</td>
<td>7</td>
<td>9</td>
<td><code-block lang="tex">\\dots</code-block></td>
<td><code-block lang="tex">\n</code-block></td>
</tr>
<tr>
<td>perfect squares</td>
<td>1</td>
<td>4</td>
<td>9</td>
<td>16</td>
<td>25</td>
<td><code-block lang="tex">\\dots</code-block></td>
<td><code-block lang="tex">\n</code-block></td>
</tr>
<tr>
<td></td>
<td><code-block lang="tex">\a_{1}</code-block></td>
<td><code-block lang="tex">\a_{2}</code-block></td>
<td><code-block lang="tex">\a_{3}</code-block></td>
<td><code-block lang="tex">\a_{4}</code-block></td>
<td><code-block lang="tex">\a_{5}</code-block></td>
<td><code-block lang="tex">\\dots</code-block></td>
<td><code-block lang="tex">\a_{n}</code-block></td>
</tr>
</table>



## Find the first five 

[//]: # (first five terms in sequence)
<table>
<tr><td colspan="2"><p>Write out the first five (5) terms of the sequence...</p></td></tr>
<tr>
<td>
<tip>
<p><code-block lang="tex">\a_{n} = 2n + 3</code-block></p>
<deflist collapsible="true" default-state="collapsed">
<def title="Answer">
<code-block lang="tex">
\begin{align}
a_{1} &= 2(1) + 3 \\
a_{2} &= 2(2) + 3 \\
a_{3} &= 2(3) + 3 \\
a_{4} &= 2(4) + 3 \\
a_{5} &= 2(5) + 3 \\
\end{align}
</code-block>
<p>first five terms of the sequence...</p>
<code-block lang="tex"> \{ 5, 7, 9, 11, 13 \}</code-block>
</def>
</deflist>
</tip>
</td>
<td>
<tip>
<p><code-block lang="tex">\a_n = (-1)^n * \frac{6 - 2n}{ \sqrt{n + 1}} </code-block></p>
<deflist collapsible="true" default-state="collapsed">
<def title="Answer">
<code-block lang="tex">
\begin{align} 
a_1 &= (-1)^{1} * \frac{6 - 2(1)}{ \sqrt{(1) + 1}} &= \frac{-4}{\sqrt{-2}} &= \frac{-4 \sqrt{-2}}{2} &= \ -2 \sqrt
{-2} \\
a_2 &= (-1)^{2} * \frac{6 - 2(2)}{ \sqrt{(2) + 1}} &= \frac{2}{\sqrt{3}} &= \frac{2 \sqrt{3}}{3} \\
a_3 &= (-1)^{3} * \frac{6 - 2(3)}{ \sqrt{(3) + 1}} &= \frac{-0}{\sqrt{4}} &= 0 \\
a_4 &= (-1)^{4} * \frac{6 - 2(4)}{ \sqrt{(4) + 1}} &= \frac{-2}{\sqrt{5}} &= \frac{-2 \sqrt{5}}{5} \\
a_5 &= (-1)^{5} * \frac{6 - 2(5)}{ \sqrt{(5) + 1}} &= - \frac{-4}{\sqrt{6}} &= \frac{2 \sqrt{6}}{3} \\
\end{align}
</code-block>
<p>first five terms of the sequence...</p>
<code-block lang="tex"> \{ -2 \sqrt{-2}, \frac{2 \sqrt{3}}{3}, 0, \frac{-2 \sqrt{5}}{5}, \frac{2 \sqrt{6}}{3} \}</code-block>
</def>
</deflist>
</tip>
</td>
</tr>
</table>



## Find the n^th term

[//]: # (find the nth term)
<table>
<tr>
<td colspan="2">
<p>Write the <code-block lang="tex">\n^{th}</code-block> terms of the sequence <code-block 
lang="tex">\a_n</code-block> suggested by the pattern</p>
</td>
</tr>
<tr>
<td>
<tip>
<p><code-block lang="tex"> \frac{2}{3}, \frac{4}{9}, \frac{8}{27}, \frac{16}{81}, \dots</code-block></p>
<deflist collapsible="true" default-state="collapsed">
<def title="Answer">
<p>Find the pattern...</p>
<code-block lang="tex">
\begin{align}
\frac{2^1}{3^1}, \frac{2^2}{3^2}, \frac{2^3}{3^3}, \frac{2^4}{3^4}, \dots \\
\end{align}
</code-block>
<p>Therefore...</p>
<code-block lang="tex">
\begin{align}
a_n = \frac{2^n}{3^n} \\
= \bigg( \frac{2}{3} \bigg) ^n \\
\end{align}
</code-block>
</def>
</deflist>
</tip>
</td>
<td>
<tip>
<p><code-block lang="tex"> 2, -4, 6, -8, 10, \dots </code-block></p>
<deflist collapsible="true" default-state="collapsed">
<def title="Answer">
<code-block lang="tex">
\begin{align} 
a_1 &= (-1)^{1} * \frac{6 - 2(1)}{ \sqrt{(1) + 1}} &= \frac{-4}{\sqrt{-2}} &= \frac{-4 \sqrt{-2}}{2} &= \ -2 \sqrt
{-2} \\
a_2 &= (-1)^{2} * \frac{6 - 2(2)}{ \sqrt{(2) + 1}} &= \frac{2}{\sqrt{3}} &= \frac{2 \sqrt{3}}{3} \\
a_3 &= (-1)^{3} * \frac{6 - 2(3)}{ \sqrt{(3) + 1}} &= \frac{-0}{\sqrt{4}} &= 0 \\
a_4 &= (-1)^{4} * \frac{6 - 2(4)}{ \sqrt{(4) + 1}} &= \frac{-2}{\sqrt{5}} &= \frac{-2 \sqrt{5}}{5} \\
a_5 &= (-1)^{5} * \frac{6 - 2(5)}{ \sqrt{(5) + 1}} &= - \frac{-4}{\sqrt{6}} &= \frac{2 \sqrt{6}}{3} \\
\end{align}
</code-block>
<p>first five terms of the sequence...</p>
<code-block lang="tex"> \{ -2 \sqrt{-2}, \frac{2 \sqrt{3}}{3}, 0, \frac{-2 \sqrt{5}}{5}, \frac{2 \sqrt{6}}{3} \}</code-block>
</def>
</deflist>
</tip>
</td>
</tr>
</table>

<code-block lang="mermaid">
graph TB
   A[Decision]
   A -- Option 0 --> B[Do Something]
   A -- Option 1 --> C[Do Something Else]
</code-block>

```mermaid
sequenceDiagram
    Tech writer -->> Developer: Hi, can you check that I've described everything correctly?
    Developer -->> Junior developer: Hi, can you, please, help our TW with the task?
    Developer --x Tech writer: Sure, I've asked Garold to take care of this, it will help him to understand the logic better.
    Junior developer -->> Developer: No problem!

    Developer --> Tech writer: Adding you both to a group chat  ...
    Note right of Developer: Adding to the chat.

    Tech writer --> Junior developer: Hi, Garold!
```