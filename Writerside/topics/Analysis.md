<show-structure for="chapter,procedure" depth="2"/>

# Empirical Model

<video src="https://youtu.be/RctntWQjazw" width="900"/>

<table>
<tr>
<td>Problem</td>
<td>Algorithm</td>
<td>Program</td>
</tr>
<tr>
<td>

- a task to be performed
- best thought in terms of (well-defined) inputs and outputs
- problem definition does not impose constraints on how the problem is solved but often includes resource constraints

</td>
<td>

- a sequence of steps followed to solve a problem
- it must be correct and composed of a finite number of concrete steps
- there can be no ambiguity
- it must terminate

</td>
<td>

- a concrete implementation of an algorithm in a programming language
- it must be correct and composed of a finite number of concrete steps
- there can be no ambiguity

</td>
</tr>
<tr>
<td colspan="3">

![analysis](analysis.jpeg)
{width="900" thumbnail="true"}

</td>
</tr>
</table>

## Why analyze algorithms?

<procedure type="choices">

Prediction 
  - the performance of different algorithms
  - the resources needed by an algorithm 

Comparison
  - the performance of different algorithms
  - the resources needed by an algorithm

Debugging
  - to understand the performance of an algorithm

Selection
  - the best algorithm for a given application
  - the best algorithm for a given machine

</procedure>

## Industry

<procedure>

![image](orgs.jpeg)
{width="900" thumbnail="true"}

</procedure>

## How do we analyze algorithms?

<procedure>

Empirical Analysis
- run the algorithm on a computer and measure the resources used
- easy to implement
- machine dependent
- not always accurate / possible

Theoretical Analysis
- analyze the algorithm using mathematical tools
- machine independent
- not always easy to implement
- not always accurate

</procedure>

<table>
<tr>
<td>
<procedure>
<b>Empirical Model</b>
<step><format color="Orange" style="bold">Run </format> algorithms</step>
<step><format color="GreenYellow" style="bold">Measure</format> actual runtime</step>
</procedure>
</td>
<td>
<procedure>
<b>Mathematical Model</b>
<step><format color="Gray">Analyze</format> Operations</step>
<step><format color="Gray">Develop</format> Model</step>
</procedure>
</td>
</tr>
</table>

## Empirical Analysis

<procedure>

- Run the algorithm on a computer and measure the resources used
  - run different input sizes
  - run multiple times for each input size
- Average the results
- Plot the results
  - fit a curve to the results
  - use the curve to predict the performance of the algorithm
  - use the curve to compare the performance of different algorithms
  - use the curve to select the best algorithm for a given application

</procedure>

### Euler's Number in Algorithmic Analysis

<table>
<tr>
<td colspan="3">

[e](https://youtu.be/m2MIpDrF7Es?feature=shared)
{width="900"}

</td>
<td>

Leonhard Euler (1707-1783)
</td>
</tr>
<tr>
<td colspan="3">

```tex
\begin{align}
e &= \lim_{n \to \infty} \left(1 + \frac{1}{n}\right)^n \\ \\
  &= \frac{1}{0!} + \frac{1}{1!} + \frac{1}{2!} + \frac{1}{3!} + \frac{1}{4!} + \dots \\ \\
  &= 1 + \frac{1}{1} + \frac{1}{1 * 2} + \frac{1}{1 * 2 * 3} + \frac{1}{1 * 2 * 3 * 4} + \frac{1}{4!} + \dots \\ \\
  &= 2.71828182845904523536028747135266249775724709369995... \\ \\ \\
\end{align}
```

… mathematical constant that is the base of the natural logarithm. It is approximately equal to 2.71828.

<br/>

Concepts introduced by Euler
- functions
- mathematical constant
- mathematical function
- complex number

</td>
<td>

![Euler](https://personajeshistoricos.com/wp-content/uploads/2018/04/Leonhard-Euler-2-785x1024.jpg)
{width="300"}

- Swiss mathematician
- one of the greatest mathematicians of all time
- made important contributions to many areas of mathematics

</td>
</tr>
</table>

<deflist>
<def title="Visualize" collapsible="true" default-state="collapsed">
        
- [Linear Recurrance : Example 1](https://opendsa-server.cs.vt.edu/embed/LinearRecurrencesCON)
- [Linear Recurrance : Example 2](https://opendsa-server.cs.vt.edu/embed/LinearRecurrencesNCON)
</def>
</deflist>

### Analysis of Euler's Number

<table>
<tr>
<td>Euler1</td>
<td>Euler2</td>
</tr>
<tr>
<td>

```c++
long double euler1(int n) {
    long double sum = 0;
    long double fact;
    for (int i = 0 ; i <= n ; i ++) {
        fact = 1;
        for (int j = 2 ; j <= i ; j++) {
            fact *= j;
        }
        sum += (1.0 / fact);
    }

    return sum;
}
```

</td>
<td>

```c++
long double euler2(int n) {
    long double sum = 0;
    long double fact = 1;

    for (int i = 0 ; i <= n ; i++) {
        sum += (1.0 / fact);
        fact *= (i+1);
    }

    return sum;
}
```

</td>
</tr>
<tr>
<td colspan="2">

<deflist collapsible="true" default-state="collapsed">
<def title="What's the difference??">

- The time it takes to run an algorithm depends on the input size and the computer
- We want to know how the algorithm's execution time increases with the size of the input
- We want to compare the performance of different algorithms
- We want to select the best algorithm for a given application
- We want to predict the performance of an algorithm
</def>
</deflist>

</td>
</tr>
</table>


### Considering Fibonacci

<table>
<tr>
<td>
Fibonacci Sequence
</td>
<td colspan="3">
Leonardo Fibonacci (1170-1250)
</td>
</tr>
<tr>
<td colspan="3">

```tex
\begin{align}
F_0 &= 0 \\ \\
F_1 &= 1 \\ \\
F_n &= F_{n-1} + F_{n-2} \\ \\
    &= 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, \dots
\end{align}
```

</td>
<td colspan="3">

![Leonardo Fibonacci](fibonacci.jpeg)
</td>
</tr>
</table>

<table>
<tr>
<td>Iterative</td>
<td>Recursive</td>
</tr>
<tr>
<td>

```c++
uint64_t fibI(uint16_t n){
    uint64_t sum;
    uint64_t prev[] = {0,1};
    if (n < 2) return n;
    for (uint16_t i = 2; i <= n; i++) {
        sum = prev[0] + prev[1];
        prev[0] = prev[1];
        prev[1] = sum;
    }
    return sum;
}
```

</td>
<td>

```c++
uint64_t fibR (uint16_t n) {
    if (n < 2) return n;
    else return fibR(n-1) + fibR(n-2);
}
```

</td>
</tr>
<tr>
<td colspan="2">

```c++
void time_func(uint16_t n, const char *name) {
    uint64_t val;
    Clock::time_point tic,toc;
    if (! strcmp(name,"Iter")) {
        tic = Clock::now();
        val = fib_iter(n);
        toc = Clock::now();
    }
    if (! strcmp(name,"Rec")) {
        tic = Clock::now();
        val = fib_rec(n);
        toc = Clock::now();
    }
    std::cout << name << "fib(" << n << "):\t" 
              << std::fixed << std::setprecision(4) 
              << Seconds(toc-tic).count() << "sec.\tOutput:"
              << val << std::endl; 
}
    
int main (int argc, char** argv) {
    if (argc != 3) {
        std::cout << "Usage:./fib<n><alg>\n";
        std::cout << "\t<n>\tn-th term to be calculated\n";
        std::cout << "\t<alg>\t algorithm to be used(RecorIter)\n";
        return 0;
    }
    uint16_t n = (uint16_t)
    atoi(argv[1]);
    time_func(n,argv[2]);
}
```
</td>
</tr>
<tr>
<td>Hypothesis</td>
<td>Outcomes</td>
</tr>
<tr>
<td>
<img src="fib_i_r.jpeg" width="900" thumbnail="true"/>
</td>
<td>
<img src="hypothesis_graph.jpeg" width="900" thumbnail="true"/>
</td>
</tr>
</table>

### Limitations of Empirical Analysis

<procedure>

Requires implementing several algorithms for the same problem
- may be difficult and time consuming
- implementation details also play a role (one particular algorithm may be “better written”)

Requires extensive testing
- time consuming
- choice of test cases might favor one of the algorithms

Variations in hardware, software, and operating system affect analysis

</procedure>










