# Recurrence Relations

<video src="https://youtu.be/B0NtAFf4bvU" width="900"/>

## Factorial of n (n!)

<procedure>


For each positive integer `n`, the quantity `n` factorial denoted (`n!`), is defined to be the product of all the integers from `1` to `n`.

```tex
n! = n * (n-1) * (n-2) * ... * 1
```

Zero factorial is defined to be `1`.

```tex
0! = 1
```

<note>

```c++
int factorial(int n) {
    if (n == 0) {
        return 1;
    }
    return n * factorial(n - 1);
}
```

</note>

<br/>

<table>
<tr>
<td>

```tex
\frac{8!}{7!}
```

</td>
<td>

```tex
\frac{5!}{2!*3!}
```

</td>
<td>

```tex
\frac{n!}{(n-3)!}
```

</td>
</tr>
<tr>
<td>

<deflist collapsible="true" default-state="collapsed">

<def title="Solution">

```tex
\begin{align}
\frac{8!}{7!} & = \frac{8 * 7!}{7!} \\
& = 8 \\
\end{align}
```

</def>
</deflist>

</td>
<td>

<deflist collapsible="true" default-state="collapsed">

<def title="Solution">

```tex 
\begin{align}
\frac{5!}{2!*3!} & = \frac{5*4*3!}{2!*3!} \\
& = 10 \\
\end{align}
```

</def>
</deflist>

</td>
<td>

<deflist collapsible="true" default-state="collapsed">

<def title="Solution">

```tex
\begin{align}
\frac{n!}{(n-3)!} & = \frac{n*(n-1)*(n-2)*(n-3)!}{(n-3)!} \\
& = n*(n-1)*(n-2) \\
& = n^3 - 3n^2 + 2n \\
\end{align}
```

</def>
</deflist>

</td>
</tr>
</table>

</procedure>

### Use Cases

<procedure>

<table>
<tr>
<td>

<tip title="Permutations">

- gives the number of ways to select `r` elements from `n` elements when order _matters_

```tex
^nP_r = \frac{n!}{(n – r)!}
```

Example

Three different fruits are to be distributed among a group of 10 people. Find the total number of ways this can be possible.

```tex 
n = 10, r = 3 \dots
```

<deflist collapsible="true" default-state="collapsed">
<def title="Solution">

```tex
\begin {align}
^{10}P_3 &= \frac{10!}{(10 – 3)!} \\
&= \frac{10!}{7!} \\ 
&= \frac{10 × 9 × 8 × 7!}{7!} \\
&= 10 × 9 × 8 \\
&= 720
\end {align}
```
</def>
</deflist>

</tip>


</td>
<td>

<tip title="Combination">

- gives the number of ways to select `r` elements from `n` elements when order _does not matter_

```tex
^nC_r = \frac{n!}{r! (n – r)!}
```

Example

Find the number of ways 3 students can be selected from a class of 50 students.

```tex 
n = 50,\ r = 3 \dots
```

<br/><br/>

<deflist collapsible="true" default-state="collapsed">
<def title="Solution">

```tex
\begin {align}
^{50}C_3 &= \frac{50!}{3!(50 - 3)!} \\
&= \frac{50 × 49 × 48 × 47!}{3! × 47!} \\
&= \frac{50 ×49 × 48}{6} \\
&= 19,600
\end {align}
```
</def>
</deflist>

</tip>

</td>
</tr>
</table>
</procedure>

## [Recurrence Relations](https://www.math.wichita.edu/discrete-book/ch_sequences.html)

<procedure>

By itself, a recurrence does not describe the running time of an algorithm
- need a *closed-form* solution (non-recursive description)
- exact *closed-form* solution may not exist, or may be too difficult to find

For most recurrences, an asymptotic solution of the form $\Theta()$ is acceptable
- ...in the context of analysis of algorithms

</procedure>


### Methods of Solving Recurrences

<procedure>



<note>

**Unrolling**

> In the unrolling method, we repeatedly substitute the recurrence relation into itself until we reach a base case. Let's unroll the recurrence relation for a specific value of n:

```tex
\begin{align}
T(n) &= 2T \bigg(\frac{n}{2} \bigg) + n \\
&= 2 \bigg[2T \bigg(\frac{n}{4} \bigg) + \frac{n}{2} \bigg] + n \\
&= 4T \bigg(\frac{n}{4} \bigg) + 2n + n \\
&= 4 \bigg[2T \bigg(\frac{n}{8} \bigg) + \frac{n}{4} \bigg] + 2n + n \\
&= 8T \bigg(\frac{n}{8} \bigg) + 4n + 2n + n \\
&= 2^kT \bigg(\frac{n}{2^k} \bigg) + kn \\
\end{align}
```

```tex
\begin{align}
\text{We continue this process until we reach the base case,} \\
\text{which occurs when } \frac{n}{2^k} = 1. \\
\text{ Solving for k, we find that } k = log_2\ n. \\
\text{ Therefore, the final unrolled expression becomes:} \\
\end{align}
```

```tex
\begin{align}
T(n) = 2^{log_2 (n)} \ T(1) + n \ log_2 \ n \\
\end{align}
```

```tex
\begin{align}
\text{Since } T(1) \text{ is a constant,}
\text{we can simplify the expression further:} \\
\end{align}
```

```tex
\begin{align}
T(n) &= nT(1) + n\ log_2 \ n \\
&= O(n\ log_2\ n) 
\end{align}
```



```tex
\begin{align}
\text{Thus, the solution obtained through unrolling suggests that the} \\
\text{time complexity of the original recurrence relation is} \\
O(n\ log_2 (n))
\end{align}
```

</note>

<br/>

<note>

**Guessing**

> In the guessing method, we make an educated guess or hypothesis about the form of the solution based on the recurrence relation. We then use mathematical induction or substitution to prove our guess.

```tex
\begin{align}
\text{Let's guess that the solution to the recurrence relation } \\
T(n) = 2T(\frac{n}{2}) + n \text{ is } T(n) = O(n\ log\ n). \\
\end{align}
```

```tex
\begin{align}
\text{We assume that } T(k) ≤ ck\ log\ (k) \text{ for some constant } \\
c, \text{ where } k < n. \\
\text{Now, we substitute this assumption into the recurrence relation:} \\
\end{align}
```

```tex
\begin{align}
T(n) &= 2T \bigg(\frac{n}{2} \bigg) + n \\
&≤ 2  \Bigg(\ c \bigg( \frac{n}{2} \bigg)\ log\ \bigg(\frac{n}{2} \bigg) \Bigg) + n \\
&= cn\ log (n) - cn\ log (2) + n \\
&= cn\ log (n) - cn + n \\
&= cn\ log (n) + (n - cn) \\
\end{align}
```

```tex
\begin{align}
\text{To ensure that } T(n) ≤ cn\ log\ (n) \text{ holds, we need to find a value of } c \\
\text{ such that } (n - cn) ≤ 0. \text{ By choosing } c ≥ 1, \text{ we can guarantee that } T(n) ≤ cn\ log\ (n). \\
\\
\text{Hence, the solution } T(n) = O(n\ log\ (n)) \text{ satisfies the recurrence relation.}
\end{align}
```
</note>

<br/>

<note>

**Recursion Tree**

> In the recursion tree method, we draw a tree to represent the recursive calls made in the recurrence relation. Each level of the tree corresponds to a recursive call, and we analyze the work done at each level.

```tex 
\begin{align}
\text{For our example, the recursion tree for } T(n) = 2T(\frac{n}{2}) + n \\
\text{ would have a root node representing } T(n), \\
\text{two child nodes representing } T(\frac{n}{2}), \\
\text{ and so on. Each node represents a recursive call,} \\
\text{and the work done at each node is represented by the term n.} \\
\\
\text{The recursion tree will have } log_2\ (n) \\
\text{ levels since we divide the problem size by } 2 \text{ at each level.} \\
\text{At each level, the work done is } n, \text{ and there are } 2^i \\
\text{ nodes at level } i. \\
\text{Therefore, the total work at each level is } 2^i * n. \\
\\
\text{Summing up the work done at each level, we have:} \\
\\
Total work = n + 2n + 4n + ... + (n * 2^{log_2\ (n)} - 1) \\
\\
\text{This is a geometric series with a common ratio of } 2 \\
\text{ and the first term being } n. \\
\text{The sum of this series is given by:} \\
\\
Total work = n * \frac{2^{log_2\ (n)} - 1}{2 - 1} \\
= \frac{n * (n - 1)}{1} \\
= n^2 - n \\
\end{align}
```

```tex
\begin{align}
\text{Therefore, the time complexity of the recurrence relation is } O(n^2).
\end{align}
```

```tex
\begin{align}
\text{Note that in this example, the unrolling and guessing methods} \\
\text{led to a time complexity of } O(n\ log\ (n)), \\
\text{while the recursion tree method resulted in } O(n^2). \\
\text{ The discrepancy arises because the recursion tree method} \\
\text{accounts for the exact work done at each level,} \\
\text{while the other methods provide upper bounds or estimations.}
\end{align}
```

</note>

<br/>

<note>

**Master Theorem**

> The master theorem is a mathematical formula used to analyze the time complexity of divide-and-conquer algorithms. It provides a solution for recurrence relations of the form:

```tex
\begin{align}
T(n) = aT \bigg(\frac{n}{b} \bigg) + f(n)
\end{align}
```

```tex
\begin{align}
\text{Where:} \\
T(n) \text{ represents the time complexity of the algorithm, } a \text{ is the number} \\
\text{ of recursive subproblems,} \frac{n}{b} \text{ is the size of each subproblem,} \\
f(n) \text{ is the time complexity of the} \text{remaining work done outside the } \\
\text{recursive calls.}
\end{align}
```

```tex
\begin{align}
\text{The master theorem provides three cases based} \\
\text{on the relationship between } f(n) \\
\text{ and the subproblem part } aT(\frac{n}{b}).
\end{align}
```

</note>

<tip title="Case 1">

```tex 
\begin{align}
\text{If } f(n) = O(n^c) \text{ for some constant} \\
c < log_b(a), \text{ then the time complexity is dominated by} \\
\text{ the subproblem part, and the overall time complexity is given by} \\
\\
T(n) = \Theta(n^{log_b(a)})
\end{align}
```

Example

```tex
\begin{align}
T(n) = 4T \bigg(\frac{n}{2} \bigg) + n
\end{align}
```

```tex
\begin{align}
\text{Step 1 : Identify the values of } a, b, and f(n) \\
\text{In this case,} \\
a = 4 \\
b = 2 \\
f(n) = n \\
\end{align}
```

```tex
\begin{align}
\text{Step 2 : Compare f(n) with } n^{log_b(a)} \\
\text{Here, } f(n) = n \text{ and } n^{log_b(a)} = n^{log_2(4)} = n^2 \\
\text{Since } f(n) = n = n^1 < n^2 = n^{log_b(a)}, \\
\text{ we fall into Case 1 of the master theorem.}
\end{align}
```

```tex
\begin{align}
\text{Step 3 : Determine the overall time complexity} \\
\text{Using Case 1, the overall time complexity is } \\
T(n) = \Theta(n^{log_b(a)}). \\
\text{In this case, } T(n) = \Theta(n^{log_2\ (4)}) = \Theta(n^2). \\
\text{So, the overall time complexity of the algorithm in this example is } \\
\Theta(n^2), \\
\text{which means the algorithm's running time grows} \\
\text{quadratically with the input size } n.
\end{align}
```

</tip>

<tip title="Case 2">

```tex
\begin{align}
\text{If } f(n) = \Theta(n^c) \text{ for some constant} \\
c = log_b(a), \text{ then the overall time complexity is given by} \\
\\
T(n) = \Theta(n^c \ log^{k(n)})
\end{align}
```

Example

```tex
\begin{align}
T(n) = 9T \bigg(\frac{n}{3} \bigg) + n^2
\end{align}
```

```tex
\begin{align}
\text{Step 1 : Identify the values of } a, b, and f(n) \\
\text{In this case:} \\
a = 9 \ \ \ (number\ of\ sub-problems) \\
b = 3 \ \ \ (size\ of\ each\ subproblem) \\
f(n) = n^2 \ \\
\end{align}
```

```tex
\begin{align}
\text{Step 2 : Compare f(n) with } n^log_b(a) \\
\text{Here, } f(n) = n^2 \text{ and } n^{log_b(a)} = n^{log_3(9)} = n^2 \\
\text{Since } f(n) = n^2 = n^{log_b(a)}, \\
\text{ we fall into Case 2 of the master theorem.}
\end{align}
```

```tex
\begin{align}
\text{Step 3 : Determine the overall time complexity} \\
\text{Using Case 2, the overall time complexity is } \\
T(n) = Θ(n^2 \ log n)
\end{align}
```

</tip>
<tip title="Case 3">

```tex 
\begin{align}
\text{If } f(n) = \Omega(n^c) \text{ for some constant} \\
c > log_b(a), \text{ and if } f(n) \\
\text{ satisfies the regularity condition} \\
(af(\frac{n}{b}) ≤ kf(n) \text{ for some constant } k < 1 \\
\text{ and sufficiently large } n, \\
\text{then the non-recursive part dominates the time complexity,} \\
\text{and the overall time complexity is given by} \\
\\
T(n) = \Theta(f(n))
\end{align}
```

Example

```tex
\begin{align}
T(n) = 2T \bigg(\frac{n}{2} \bigg) + n^3
\end{align}
```

```tex
\begin{align}
\text{Step 1 : Identify the values of } a, b, and f(n) \\
\text{In this case, } \\
a = 2 \\
b = 2 \\
f(n) = n^3 \\
\end{align}
```

```tex
\begin{align}
\text{Step 2 : Compare f(n) with } n^log_b(a) \\
\text{Here, } f(n) = n^3 \text{ and } n^{log_b(a)} = n^{log_2(2)} = n^1 = n \\
\text{Since } f(n) = n^3 > n = n^{log_b(a)}, \text{ we fall into Case 3 of the master theorem.}
\end{align}
```

```tex
\begin{align}
\text{Step 3: Check if f(n) satisfies the regularity condition} \\
\text{In this case, we can see that } af(\frac{n}{b}) = 2(\frac{n}{2})^3 = (\frac{1}{2})n^3 \le kn^3 \\
\text{for } k = \frac{1}{2} \text{ and sufficiently large } n. \\
\text{The regularity condition is satisfied.}
\end{align}
```

```tex
\begin{align}
\text{Step 4 : Determine the overall time complexity.} \\
\text{Using Case 3, the overall time complexity is } \\
T(n) = Θ(n^3)
\end{align}
```

</tip>

<note>

_It’s important to note that the Master Theorem is applicable in specific cases, and not all recurrence relations can be solved using this theorem. However, for recurrence relations that follow the prescribed form, it provides a convenient way to determine the time complexity._
</note>

</procedure>

### Examples

<procedure>
<tabs>
<tab title="Dividing Function">

<note>

```c++
void Test(int n) {       // = T(n)
  if (n > 0) {
    printf("/d", n);     // = 1
    Test(n/2);           // = T(n/2) 
  }
}
```

<br/>

```tex
T(n) =
\begin{cases}
1,  & \text{$n = 1$}  \\[2ex]
T(\frac{n}{2}) + 1, & \text{$n \gt 1$}
\end{cases}
```
</note>

<deflist collapsible="true" default-state="collapsed">
<def title="Unrolling" default-state="expanded">

```tex
\text{Let's unroll the recurrence relation step by step:}  \\ \\
```

```tex
\begin{align}
Step\ 1 : \ T(n) & = T(\frac{n}{2}) + c \\
Step\ 2 : \ T(n) & =  \bigg[T(\frac{n}{4}) + c \bigg] + c \\
& = T\bigg(\frac{n}{4}\bigg) + 2c \\
Step\ 3 : \ T(n) & =  \bigg[T\bigg(\frac{n}{8}\bigg) + c \bigg] + 2c \\
& = T\bigg(\frac{n}{8}\bigg) + 3c \\
\end{align}
```

```tex
\begin{align}
\text{Continuing this process, we can unroll the recurrence relation up to k steps: } \\
T(n) = T \bigg(\frac{n}{2^k} \bigg) + kc \\
\end{align}
```

```tex
\begin{align}
\text{We keep unrolling until we reach the base case, which occurs when } \\
\frac{n}{2^k} = 1 \\
\end{align}
```

```tex
\begin{align}
\text{Solving for } k, \text{ we find that } \\
k = log_2\ (n) \\
\end{align}
```

```tex
\begin{align}
\text{Now, let's substitute this value of } k \text{ into the unrolled relation:} \\
T(n) = T(\frac{n}{2^{log_2\ (n)}}) + log_2\ (n)c \\
\end{align}
```

```tex
\begin{align}
\text{Since } \frac{n}{2^{log_2\ (n)}} = 1, \text{ we simplify further:} \\
T(n) = T(1) + log_2\ (n)c \\
\end{align}
```

```tex
\begin{align}
\text{Since } T(1) \text{ is a constant time complexity for the base case } \\
\text{of a binary search, we can replace it with a constant, say } d: \\
T(n) = d + log_2\ (n)c \\
\end{align}
```

```tex
\begin{align}
\text{Finally, we can simplify this expression as:} \\
T(n) = O(log\ n) \\
\end{align}
```

```tex
\begin{align}
\text{Therefore, after unrolling the recurrence relation for binary} \\
\text{search, we obtain the time complexity of } \\
O(log\ n) \\
\end{align}
```

```tex
\begin{align}
\text{This analysis shows that the time complexity of a binary search} \\
\text{algorithm is logarithmic with respect to the size of the array} \\
\text{being searched, which aligns with the intuitive understanding} \\
\text{of the algorithm's efficiency.}  \\
\end{align}
```

</def>
<def title="Guessing">

```tex
\begin{align}
\text{Let's make a guess or hypothesis about the form of the solution} \\
\text{based on the recurrence relation } \\
\\
T(n) = T\bigg(\frac{n}{2}\bigg) + 1. \\
\end{align}
```

```tex
\begin{align}
\text{Let's assume that } T(n) = O(log\ (n)). \\
\\
\text{We assume that } T(k) ≤ c\ log\ (k) \text{ for some constant } c, \text{where } k < n. \\
\text{Now, let's substitute this assumption into the recurrence relation:} \\
\end{align}
```

```tex
\begin{align}
T(n) &= T \bigg(\frac{n}{2} \bigg) + 1 \\
&≤ c\ log\ \frac{n}{2} + 1 \\
&= c\bigg(log\ (n) - 1\bigg) + 1 \\
&= c\ log\ (n) + 1 + c \\
&= c\ log\ (n) + (1 - c) \\
\end{align}
```
```tex
\begin{align}
\text{To ensure that } T(n) ≤ c\ log\ (n) \text{ holds, we need to find a value of } c \text{ such} \\
\text{that } (1 - c) ≤ 0. \text{ By choosing } c ≥ 1, \text{ we can guarantee that } T(n) ≤ c\ log\ (n). \\
\\
\text{Hence, the solution } T(n) = O(log\ n) \text{ satisfies the recurrence relation.}
\end{align}
```

</def>
<def title="Recursion Tree">

```tex 
\begin{align}
\text{At each level of the recursion tree, we divide the problem size by 2,} \\
\text{following the recurrence relation } \\
T(n) = T\bigg(\frac{n}{2}\bigg) + 1 \\
\\
\text{The work done at each level is constant, represented by the "+ 1" term.} \\
\\
\text{Let's start with the initial value } T(n) \text{ and recursively split} \\
\text{it into smaller sub-problems} \\
\end{align}
```

```tex
\begin{align}
\text{And so on...} \\
\\
\text{The recursion tree will have } log_2\ (n) \text{ levels since we divide the problem} \\
\text{size by } 2 \text{ at each level. At each level, the work done is a constant "+ 1".} \\
\text{The total work done can be calculated by summing up the work at each level:} \\
\\
Total work = 1 + 1 + 1 + ... + 1\ (log_2\ (n)\ times) \\
= log_2\ (n) \\
\\
\text{Therefore, the time complexity of the recurrence relation } T(n) = T\bigg(\frac{n}{2}\bigg) + 1 \\
\text{analyzed using the recursion tree method is } O(log\ n). \\
\\
\text{The recursion tree method provides a direct visualization of the recursive calls} \\
\text{and the corresponding work done at each level, allowing us to analyze the time} \\
\text{complexity of the recurrence relation.}
\end{align}
```

</def>
<def title="Master Theorem">

```tex 
\begin{align}
\text{The Master Theorem provides a framework for solving recurrence relations} \\
\text{of the form } \\
T(n) = aT\bigg(\frac{n}{b}\bigg) + f(n), \text{ where } a ≥ 1, b > 1, \text{ and } f(n) \text{ is a function.} \\
\\
\text{In our case, } T(n) = T\bigg(\frac{n}{2}\bigg) + 1, \text{ where } a = 1, b = 2, \text{ and } f(n) = 1. \\
\\
\text{Comparing } f(n) = 1 \text{ with } n^{log_b\ (a)}: \\
\\
f(n) = 1, \text{ which is equal to } n^{log_2\ (1)} = n^0 = 1. \\
\\
\text{According to the Master Theorem:} \\
\\
\text{If } f(n) = \Theta(n^{log_b\ (a)} * log^{k(n)}) \\
\text{ where } k ≥ 0, \text{ then } \\
T(n) = \Theta(n^{log_b\ (a)} * log^{k+1}\ (n)). \\
\text{In our case, } f(n) = \Theta(1) \\
\text{ which falls under the second case.} \\
\text{Therefore, the time complexity of the recurrence relation } \\
T(n) = T\bigg(\frac{n}{2}\bigg) + 1 \\
\text{ is } \Theta(n^{log_2\ (1)} * log^{0+1}\ (n)) = \Theta(log\ (n)). \\
\\
\text{Thus, according to the Master Theorem,} \\
\text{the time complexity of the recurrence relation } \\
T(n) = T\bigg(\frac{n}{2}\bigg) + 1 \text{ is } \Theta(log\ (n)), \\
\text{ which aligns with the results obtained from unrolling,} \\
\text{guessing, and the recursion tree.} \\
\\
\text{All four methods provide consistent solutions,} \\
\text{indicating that the time complexity} \\
\text{of the recurrence relation } \\
T(n) = T\bigg(\frac{n}{2}\bigg) + 1 \text{ is } O(log\ n). \\
\end{align}
```

</def>
</deflist>
</tab>
<tab title="Linear">

<note>

```c++
void Test(int n) {       // = T(n)
  if (n > 0) {
    printf("/d", n);     // = 1
    Test(n - 1);         // = T(n - 1) 
  }
}
```

<br/>

```tex
T(n) =
\begin{cases}
1,  & \text{$n\ = 0$}  \\[2ex]
T(n - 1) + 1, & \text{$n\ \gt 0$}
\end{cases}
```
</note>

<deflist collapsible="true" default-state="collapsed">
<def title="Unrolling">

```tex
\begin{align}
\text{Let's unroll the recurrence relation step by step:}  \\ \\
\end{align}
```
    
```tex
\begin{align}
Step\ 1 : \ & T(n)  = T(n - 1) + 1 \\
Step\ 2 : \ & T(n)  = [T(n - 2) + 1] + 1 \\
& = T(n - 2) + 2 \\
Step\ 3 : \ & T(n)  = [T(n - 3) + 1] + 2 \\
&  = T(n - 3) + 3 \\
\end{align}
```

```tex
\begin{align}
\text{Continuing this process, we can unroll the recurrence relation up to k steps:} \\
T(n) = T(n - k) + k \\
\end{align}
```

```tex
\begin{align}
\text{We keep unrolling until we reach the base case, which occurs when } \\
n - k = 0 \\
\end{align}
```

```tex
\begin{align}
\text{Solving for } k, \text{ we find that } \\
k = n \\
\end{align}
```

```tex
\begin{align}
\text{Now, let's substitute this value of } k \text{ into the unrolled relation:} \\
T(n) = T(0) + n \\
\end{align}
```

```tex
\begin{align}
\text{Since } T(0) \text{ represents the time complexity for the base case, which is a constant,} \\
\text{we can replace it with a constant, say } c: \\
T(n) = c + n \\
\end{align}
```

```tex
\begin{align}
\text{Finally, we can simplify this expression as:} \\
T(n) = O(n) \\
\end{align}
```

```tex
\begin{align}
\text{Therefore, the solution obtained through unrolling suggests that the} \\
\text{time complexity of the recurrence relation } \\
T(n) = T(n - 1) + 1 \text{ is } O(n). \\
\end{align}
```

</def>
<def title="Guessing" default-state="expanded">

```tex
\begin{align}
\text{Let's make a guess or hypothesis about the form of the solution based} \\
\text{on the recurrence relation } T(n) = T(n - 1) + 1. \\
\\
\text{Let's assume that } T(n) = O(n). \\
\\
\text{We assume that } T(k) ≤ ck \text{ for some constant } c, \\
\text{ where } k < n. \text{ Now, let's substitute this assumption into the recurrence relation:} \\
\end{align}
```

```tex
\begin{align}
T(n) & = T(n - 1) + 1 \\
& ≤ c(n - 1) + 1 \\
& = cn - c + 1 \\
\end{align}
```

```tex
\begin{align}
\text{To ensure that } T(n) ≤ cn \text{ holds, we need to find a value of } c \\
\text{ such that } (-c + 1) ≤ 0. \text{ By choosing } c ≥ 1, \\
\text{ we can guarantee that } T(n) ≤ cn. \\
\\
\text{Hence, the solution } T(n) = O(n) \text{ satisfies the recurrence relation.}
\end{align}
```

</def>
<def title="Recursion Tree">

```tex 
\begin{align}
\text{Let's draw a recursion tree to represent the recursive calls made} \\
\text{in the recurrence relation } T(n) = T(n - 1) + 1. \\
\text{ Each level of the tree corresponds to a recursive call,} \\
\text{and we analyze the work done at each level.} \\
\\
\text{The recursion tree will have n levels since we subtract } 1 \text{ from } n \\
\text{ at each level. At each level, the work done is } 1, \\
\text{ and there is only one node at each level.} \\
\text{Therefore, the total work at each level is } 1. \\
\\
\text{Summing up the work done at each level, we have:} \\
\\
Total work = 1 + 1 + 1 + ... + 1\ (n\ times) \\
= n \\
\\
\text{Therefore, the time complexity of the recurrence relation is } O(n). \\
\end{align}
```

</def>
<def title="Master Theorem">

```tex 
\begin{align}
\text{The Master Theorem is not applicable to the recurrence relation } \\
T(n) = T(n - 1) + 1 \text{ because it is not in the required form of } \\
T(n) = aT(\frac{n}{b}) + f(n). \\
\\
\text{Therefore, the Master Theorem cannot be directly used to solve this recurrence relation.} \\
\\
\text{To summarize, the analysis using unrolling, guessing, recursion tree,} \\
\text{and the Master Theorem (where applicable) all yield a time complexity of } O(n) \\
\text{for the recurrence relation } T(n) = T(n - 1) + 1. \\
\end{align}
```

</def>
</deflist>
</tab>
<tab title="Divide and Conquer">

<note>

```c++
void Test(int n) {              // = T(n)
  if (n > 1) {
    for(i = 0; i < n; i++>) {   // = n
      // some statement
    }
    Test(n/2);                  // = T(n/2)
    Test(n/2);                  // = T(n/2)
  }
}
```

<br/>

```tex
T(n) = 
\begin{cases}
1,  & \text{$n\ = 1$}  \\[2ex]
2T(\frac{n}{2}) + n, & \text{$n\ \gt 1$}
\end{cases}
```
</note>

<deflist collapsible="true" default-state="collapsed">
<def title="Unrolling">




```tex
\begin{align}
\text{Let's unroll the recurrence relation step by step:} \\ \\
\end{align}
```

```tex
\begin{align}
Step\ 1 : \ & T(n)  = 2T \bigg(\frac{n}{2} \bigg) + n \\
Step\ 2 : \ & T(n)  = 2\bigg[2T \bigg(\frac{n}{4} \bigg) + \frac{n}{2}\bigg] + n \\
& = 4T \bigg(\frac{n}{4} \bigg) + 2n \\
Step\ 3 : \  T(n) & = \bigg[T \bigg(\frac{n}{8} \bigg) + \frac{n}{4} + \frac{n}{2}\bigg] + 4n \\
&  = 8T \bigg(\frac{n}{8} \bigg) + 4n \\
\\
Step\ k : \ & T(n) = 2^{k}\ T \bigg( \frac{n}{2^k} \bigg) + kn \\ \\
\\
T(n) &= 2^{log_2\ n}\ T \bigg(\frac{n}{2^{log_2\ n}} \bigg) + n\ log_2\ n \\
&= nT(1) + n\ log_2\ n \\
&= n + n\ log_2\ n \\
\\
T(n) &= c + n + n\ log_2\ n \\
\\
T(n) &= O(n\ log\ n) \\
\end{align}
```

```tex
\begin{align}
\text{Therefore, the solution obtained through unrolling suggests that the} \\
\text{time complexity of the recurrence relation } T(n) = 2T\bigg(\frac{n}{2}\bigg) + n \text{ is } O(n\ log\ n). \\
\end{align}
```

</def>
<def title="Guessing">

```tex 
\begin{align}
\text{Let's make a guess or hypothesis about the form of the solution based} \\
\text{on the recurrence relation } T(n) = 2T\bigg(\frac{n}{2}\bigg) + n. \\
\\
\text{Let's assume that } T(n) = O(n\ log\ n). \\
\\
\text{We assume that } T(k) ≤ ck\ log\ (k) \text{ for some constant } c, \\
\text{where } k < n. \text{ Now, let's substitute this assumption into the recurrence relation:} \\
\end{align}
```

```tex
\begin{align}
T(n) &= 2T \bigg(\frac{n}{2} \bigg) + n \\
&≤ 2c \bigg(\frac{n}{2} \bigg)\ log\ \bigg(\frac{n}{2} \bigg) + n \\
&= cn\ log\ \bigg(\frac{n}{2} \bigg) + n \\
&= cn\ log\ (n) - cn\ log\ (2) + n \\
&= cn\ log\ (n) - cn + n \\
\end{align}
```

```tex
\begin{align}
\text{To ensure that } T(n) ≤ cn\ log\ (n) \text{ holds, we need to find a value of } c \\
\text{ such that } (-cn + n) ≤ 0. \text{ By choosing } c ≥ 1, \text{ we can guarantee that } T(n) ≤ cn\ log\ (n). \\
\\
\text{Hence, the solution } T(n) = O(n\ log\ n) \text{ satisfies the recurrence relation.}
\end{align}
```

</def>
<def title="Recursion Tree">

```tex 
\begin{align}
\text{Let's draw a recursion tree to represent the recursive calls made} \\
\text{in the recurrence relation } T(n) = 2T\bigg(\frac{n}{2}\bigg) + n. \\
\text{Each level of the tree corresponds to a recursive call,} \\
\text{and we analyze the work done at each level.} \\
\end{align}
```

```tex
\begin{align}
\text{The recursion tree will have } log_2\ (n) \text{ levels since we divide} \\
\text{the problem size by } 2 \text{ at each level.} \\
\text{At each level, the work done is } n, \text{ and there are } \\
2^i \text{ nodes at level } i. \\
\text{Therefore, the total work at each level is } n * 2^i. \\
\\
\text{Summing up the work done at each level, we have:} \\
\end{align}
```

```tex
\begin{align}
Total work = n + 2n + 4n + ... + (2^{log_2\ (n) - 1}\ n) \ \ \\
\end{align}
```

```tex
\begin{align}
\text{This is a geometric series with a common ratio of 2 and the} \\
\text{first term being } n. \text{ The sum of this series is given by:} \\
\end{align}
```

```tex
\begin{align}
Total work = n * \frac{2^{log_2\ (n)}\ - 1}{2 - 1} \\
= n * {2^{log₂(n)}\ - 1} \\
= n * (n - 1) \\
= n^2 - n \\
\end{align}
```

```tex
\begin{align}
\text{Therefore, the time complexity of the recurrence relation is } O(n^2). \\
\end{align}
```

</def>
<def title="Master Theorem" default-state="expanded">

```tex 
\begin{align}
\text{The Master Theorem is applicable to the recurrence relation } \\
\end{align}
```

```tex
\begin{align}
T(n) = 2T\bigg(\frac{n}{2}\bigg) + n. \text{ We can express it in the form } \\
T(n) = aT\bigg(\frac{n}{b}\bigg) + f(n) \text{ with } a = 2, b = 2, \text{ and } f(n) = n. \\
\end{align}
```

```tex 
\begin{align}
\text{Comparing } f(n) = n \text{ with } n^{log_b\ (a)}: f(n) = n, \\ 
\text{ which is smaller than } n^{log_2\ (2)} = n. \\
\\
\text{According to the Master Theorem:} \\
\\
\text{If } f(n) = O(n^c) \text{ for some constant } c < log_b\ (a), \\
\text{ then } T(n) = Θ(n^{log_b\ (a)}). \\
\text{In our case, } f(n) = O(n^1) = O(n), \text{ which falls under the first case.} \\
\text{Therefore, the time complexity of the recurrence relation } \\
\end{align}
```

```tex
\begin{align}
T(n) = 2T\bigg(\frac{n}{2}\bigg) + n \text{ is } Θ(n^{log_2\ (2)}) = Θ(n). \\
\end{align}
```

```tex 
\begin{align}
\text{Thus, according to the Master Theorem, the time complexity of the} \\
\text{recurrence relation } T(n) = 2T\bigg(\frac{n}{2}\bigg) + n \text{ is } \\
Θ(n), \text{ which aligns with the results obtained from unrolling,} \\
\text{guessing, and the recursion tree.} \\
\\
\text{All four methods provide consistent solutions,} \\
\text{indicating that the time complexity} \\
\text{of the recurrence relation } \\
T(n) = 2T\bigg(\frac{n}{2}\bigg) + n \text{ is } O(n\ log\ n). \\
\end{align}
```

</def>
</deflist>
</tab>
<tab title="Tower of Hanoi">

<note>

```c++
void Test(int n) {    // = T(n)
  printf("/d", n);    // = 1
  Test(n - 1);        // = T(n - 1)
  Test(n - 1);        // = T(n - 1)
}
```

<br/>

```tex
T(n) =
\begin{cases}
1,  & \text{$n\ = 0$}  \\[2ex]
2T(n - 1) + 1, & \text{$n\ \gt 0$}
\end{cases}
```
</note>

<deflist collapsible="true" default-state="collapsed">
<def title="Unrolling">

```tex
\begin{align}
\text{Let's unroll the recurrence relation step by step:}  \\ \\
\end{align}
```

```tex
\begin{align}
Step\ 1 : \ & T(n)  = 2T(n - 1) + 1 \\
Step\ 2 : \ & T(n)  = 2[2T(n - 2) + 1] + 1 \\
& = 4T(n - 2) + 3 \\
Step\ 3 : \ & T(n)  = 2[2[2T(n - 3) + 1] + 1] + 1 \\
&  = 8T(n - 3) + 7 \\
\end{align}
```

```tex
\begin{align}
Step\ k: &  T(n) = 2^{k}\ T(n - k) + (2^k - 1)
\end{align}
```

```tex
\begin{align}
\text{We keep unrolling until we reach the base case, which occurs when } \\
n - k = 1. \text{ Solving for } k, \text{ we find that } k = n - 1. \\
\end{align}
```

```tex
\begin{align}
T(n) &= 2^{n - 1}\ T(1) + (2^{n - 1} - 1) \\
&= 2^{n - 1} + (2^{n - 1} - 1) \\
&= 2^n - 1 \\
\end{align}
```

```tex
\begin{align}
\text{Therefore, the solution obtained through unrolling suggests that the} \\
\text{time complexity of the recurrence relation } T(n) = 2T(n - 1) + 1 \text{ is } O(2^n). \\
\end{align}
```

</def>
<def title="Guessing">

```tex
\begin{align}
\text{Let's make a guess or hypothesis about the form of the solution based} \\
\text{on the recurrence relation } T(n) = 2T(n - 1) + 1. \\
\\
\text{Let's assume that } T(n) = O(2^n). \\
\\
\text{We assume that } T(k) ≤ c * 2^k \text{ for some constant } c, \\
\text{where } k < n. \text{ Now, let's substitute this assumption into the recurrence relation:} \\
\end{align}
```

```tex
\begin{align}
T(n) &= 2T(n - 1) + 1 \\
&≤ 2(c * 2^{n - 1}) + 1 \\
&= c * 2^n + 1 \\
\end{align}
```

```tex
\begin{align}
\text{To ensure that } T(n) ≤ c * 2^n \text{ holds, we need to find a value of } c \\
\text{ such that } (c + 1) ≤ c. \text{ This is not possible, so our assumption is incorrect.} \\
\\
\text{Hence, we cannot prove the solution } T(n) = O(2^n) \text{ using the guessing method.}
\end{align}
```

</def>
<def title="Recursion Tree" default-state="expanded">

```tex 
\begin{align}
\text{Let's draw a recursion tree to represent the recursive calls made} \\
\text{in the recurrence relation } T(n) = 2T(n - 1) + 1. \\
\text{Each level of the tree corresponds to a recursive call,} \\
\text{and we analyze the work done at each level.} \\
\end{align}
```

```tex
\begin{align}
\text{The recursion tree will have n levels since we subtract } 1 \text{ from } n \\
\text{ at each level. At each level, the work done is } 1, \text{ and there are } \\
2^i \text{ nodes at level } i. \\
\text{Therefore, the total work at each level is } 1 * 2^i. \\
\\
\text{Summing up the work done at each level, we have:} \\
\end{align}
```

```tex
\begin{align}
Total work = 1 + 2 + 4 + ... + 2^{n - 1} \\
= 2^n - 1 \\
\end{align}
```

```tex
\begin{align}
\text{Therefore, the time complexity of the recurrence relation is } O(2^n). \\
\end{align}
```

</def>
<def title="Master Theorem">

```tex 
\begin{align}
\text{The Master Theorem is not directly applicable to the recurrence relation } \\
T(n) = 2T(n - 1) + 1 \text{ because it is not in the required form of } \\
T(n) = aT(\frac{n}{b}) + f(n). \\
\\
\text{Therefore, the Master Theorem cannot be used to directly} \\
\text{solve this recurrence relation.} \\
\\
\text{To summarize, the analysis using unrolling, guessing, recursion tree,} \\
\text{and the Master Theorem (where applicable) all yield a time complexity of } O(2^n) \\
\text{for the recurrence relation } T(n) = 2T(n - 1) + 1. \\
\end{align}
```

</def>
</deflist>
</tab>
</tabs>
</procedure>