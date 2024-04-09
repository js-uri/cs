# Dynamic Programming


<tabs>
<tab title="Part 1">

<video src="https://www.youtube.com/watch?v=Hdr64lKQ3e4" preview-src="dp1.jpeg" width="900" />
</tab>
<tab title="Part 2">

<video src="https://youtu.be/rE5h11FwiVw?feature=shared" preview-src="dp2.jpeg" width="900" />
</tab>
</tabs>


## Defined

> Dynamic programming is a method for solving complex problems by breaking them down into simpler subproblems. It is a powerful technique that can be used to solve a wide range of problems, from optimization to sequence alignment. Dynamic programming is based on the principle of optimal substructure, which states that an optimal solution to a problem can be constructed from optimal solutions to its subproblems.

{ style="note" }

## Key Aspects

<table>
<tr>
<td>

**Overlapping Subproblems**

</td>
<td>

**Optimal Substructure**

</td>
</tr>
<tr>
<td>

Many problems have overlapping subproblems, which means that the same subproblem is solved multiple times. Dynamic programming avoids this redundancy by solving each subproblem only once and storing the solution for future use.

</td>
<td>

Dynamic programming relies on the principle of optimal substructure, which states that an optimal solution to a problem can be constructed from optimal solutions to its subproblems. This property allows dynamic programming to efficiently solve complex problems by breaking them down into simpler subproblems.

</td>
</tr>
</table>

### Application & Approaches

<table>
<tr>
<td>

**Memoization**

</td>
<td>

**Tabulation**

</td>
</tr>
<tr>
<td>

Memoization is a technique used in dynamic programming to store the results of subproblems and reuse them when needed. This helps to avoid redundant calculations and improve the efficiency of the algorithm.

</td>
<td>

Tabulation is a bottom-up approach to dynamic programming that solves the problem by iteratively computing the solutions to subproblems. This approach is often used in problems where the optimal solution can be constructed from the solutions to smaller subproblems.

</td>
</tr>
</table>

<table>
<tr>
<td>

**Top-Down Approach**

</td>
<td>

**Bottom-Up Approach**

</td>
</tr>
<tr>
<td>

The top-down approach is a recursive method that starts with the main problem and breaks it down into smaller subproblems. It then solves each subproblem recursively and stores the results in a memo array for future use. This approach is often used in problems where the optimal solution can be constructed from the solutions to smaller subproblems.

</td>
<td>

The bottom-up approach is a common strategy in dynamic programming where the algorithm starts by solving the smallest subproblems and works its way up to the main problem. This approach is often used in problems where the optimal solution can be constructed from the solutions to smaller subproblems.

</td>
</tr>
</table>


### Fibonacci Sequence

<procedure>

**Approaches**

<tabs>
<tab title="Fibonacci numbers">

> 
>
> ```tex
> F(1) = F(2) = 1
> ```
>  
> <br/>
> 
> ```tex
> F(n) = F(n-1) + F(n-2)
> ```
>
> <br/>
>
> ```tex
> Goal : Compute \ F(n)
> ```

</tab>
<tab title="Naive Recursion">

> The recursive approach to computing the Fibonacci sequence is a simple and intuitive method that uses the definition of the sequence to calculate each element. However, this approach is not efficient for large values of n due to the exponential growth in the number of function calls.

<br/>

```python
import sys

def fibonacci(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        return fibonacci(n-1) + fibonacci(n-2)
    
if __name__ == "__main__":
    print(fibonacci(5))
    print(fibonacci(20))
    print(fibonacci(40))
```


<deflist collapsible="true">
<def title="Time Complexity">

The time complexity of the recursive approach is O(2^n), where n is the number of elements in the Fibonacci sequence. This is because each call to the fibonacci function results in two more calls, leading to an exponential growth in the number of function calls.
</def>
</deflist>

</tab>
<tab title="Memoization">

> The memoization approach is a technique used in dynamic programming to store the results of subproblems and reuse them when needed. This helps to avoid redundant calculations and improve the efficiency of the algorithm.

<br/>

```python
import sys

def fibonacci(n, memo={}):
    if n in memo:
        return memo[n]
    if n == 0:
        return 0
    elif n == 1:
        return 1
    else:
        memo[n] = fibonacci(n-1, memo) + fibonacci(n-2, memo)
        return memo[n]
    
if __name__ == "__main__":
    print(fibonacci(40))
    print(fibonacci(100))
    print(fibonacci(1000))
```


<deflist collapsible="true">
<def title="Time Complexity">

The time complexity of the memoization approach is O(n), where n is the number of elements in the Fibonacci sequence. This is because each element in the sequence is computed only once and stored in the memo array for future use.
</def>
</deflist>

</tab>
<tab title="Bottom-Up">

> The bottom-up approach is a common strategy in dynamic programming where the algorithm starts by solving the smallest subproblems and works its way up to the main problem. This approach is often used in problems where the optimal solution can be constructed from the solutions to smaller subproblems.

<br/>

```python
import sys

def fibonacci(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    a, b = 0, 1
    for i in range(2, n+1):
        a, b = b, a + b
    return b

if __name__ == "__main__":
    print(fibonacci(100))
    print(fibonacci(1000))
    print(fibonacci(10000))
```


<deflist collapsible="true">
<def title="Time Complexity">

The time complexity of the bottom-up approach is O(n), where n is the number of elements in the Fibonacci sequence. This is because each element in the sequence is computed only once, starting from the base cases and working up to the desired element.
</def>
</deflist>

</tab>
</tabs>

*_Note : all examples in Python as g++ is not accurately compiling for large numbers_*

</procedure>

### Classic Examples of Dynamic Programming

<table>
<tr>
<td></td>
<td></td>
</tr>
<tr>
<td>

**Longest Common Subsequence**

</td>
<td>

The longest common subsequence problem is a classic example of dynamic programming that involves finding the longest subsequence that is common to two sequences. This problem can be solved using dynamic programming by breaking it down into smaller subproblems and computing the solutions iteratively.

</td>
</tr>
<tr>
<td>

**Knapsack Problem**

</td>
<td>

The knapsack problem is another classic example of dynamic programming that involves finding the optimal selection of items to maximize the value while staying within a given weight limit. This problem can be solved using dynamic programming by considering the value and weight of each item and computing the optimal solution iteratively.

</td>
</tr>
<tr>
<td>

**Edit Distance**

</td>
<td>

The edit distance problem is a classic example of dynamic programming that involves finding the minimum number of operations required to transform one string into another. This problem can be solved using dynamic programming by considering the cost of each operation and computing the optimal solution iteratively.

</td>
</tr>
<tr>
<td>

**Matrix chain multiplication**

</td>
<td>

The matrix chain multiplication problem is a classic example of dynamic programming that involves finding the optimal way to multiply a sequence of matrices to minimize the number of scalar multiplications. This problem can be solved using dynamic programming by considering the cost of each multiplication and computing the optimal solution iteratively.

</td>
</tr>
<tr>
</tr>
<tr>
<td>

**Shortest path algorithms like Floyd-Warshall and Bellman-Ford**

</td>
<td>

The shortest path algorithms like Floyd-Warshall and Bellman-Ford are classic examples of dynamic programming that involve finding the shortest path between two nodes in a graph. These problems can be solved using dynamic programming by considering the cost of each edge and computing the optimal solution iteratively.

</td>
</tr>
<tr>
</tr>
</table>

## Advantages & Disadvantages

<table>
<tr>
<td>✅</td>
<td>❌</td>
</tr>
<tr>
<td>can be used to solve a wide range of problems, from optimization to sequence alignment</td>
<td>challenging to implement and understand, especially for beginners</td>
</tr>
<tr>
<td>based on the principle of optimal substructure, which allows it to efficiently solve complex problems by breaking them down into simpler subproblems.</td>
<td>computationally expensive for problems with a large number of subproblems</td>
</tr>
<tr>
<td>can lead to significant improvements in time complexity compared to naive recursive approaches</td>
<td>memory-intensive for problems with a large number of subproblems</td>
</tr>
<tr>
<td>can be implemented using memoization or tabulation, depending on the problem and the specific requirements.</td>
<td>difficult to optimize for problems with complex dependencies between subproblems</td>
</tr>
<tr>
<td>is a powerful technique that can be used to solve problems in various domains, including computer science, mathematics, and engineering.</td>
<td>difficult to debug and test due to the complexity of the algorithm and the large number of subproblems involved</td>
</tr>
</table>


## Complexity Analysis

> The time and space complexity of a dynamic programming solution depends on the problem and the specific implementation (memoization or tabulation). However, dynamic programming solutions often lead to significant improvements in time complexity compared to naive recursive approaches. 

