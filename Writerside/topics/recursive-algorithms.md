<show-structure for="chapter,procedure" depth="2"/>

# Recursive Algorithms

<tabs>
<tab title="What is it?">
<video src="https://youtu.be/6oDQaB2one8" width="900" preview-src="headscratch.jpeg"/>
</tab>
<tab title="Loops v. Recursion">
<video src="https://youtu.be/HXNhEYqFo0o" width="900" preview-src="recalgo1.jpeg"/>
</tab>
</tabs>

## Iteration v. Recursion

<procedure>

<compare first-title="Iterative" second-title="Recursive" style="left-right">

```c++

// The iterative function factorialIterative calculates the factorial by
// using a loop. It initializes result to 1 and then iterates over the
// numbers from 1 to n, multiplying each number with the current value
// of result to accumulate the factorial.

#include &lt;iostream>

int factorialIterative(int n) {
    int result = 1;
    for (int i = 1; i <= n; ++i) {
        result *= i;
    }
    return result;
}
```

```c++
// The recursive function factorialRecursive calculates the factorial by
// breaking down the problem into smaller sub-problems. The base case is
// when n equals 0, and for any other value of n, the factorial is
// computed by multiplying n with the factorial of n-1.

#include &lt;iostream>

int factorialRecursive(int n) {
    if (n == 0)
        return 1;
    else
        return n * factorialRecursive(n - 1);
}
```

</compare>
</procedure>

## Recursion

<tabs>
<tab title="Premise">

<procedure type="choices">

![image](https://cdn.slidesharecdn.com/ss_thumbnails/recursion-130206094649-phpapp01-thumbnail-4.jpg?cb=1360144228)

<p>The process of solving a problem by reducing it to smaller versions of itself</p>
<step>Solve a task by reducing it to smaller tasks (of the same structure)</step>
<step>Technically, a recursive function is one that calls itself</step>
</procedure>


</tab>
<tab title="General Form">

<procedure>

```c++
int someFunction() {
    if (base_case) {
        // calculate trivialSolution       
    } else {
        // break task into subtasks
        // solve each task recursively
        // merge solutions if necessary
    }
}
```

<table>
<tr>
<td>
<deflist>
<def title="Base Case">

- solution for a trivial case
- it can be used to stop the recursion (prevents “stack overflow”)
- every recursive algorithm needs at least one base case
</def>
<def title="Recursive Calls">

- divide problem into smaller instance(s) of the same structure
</def>
</deflist>
</td>
<td>
</td>
</tr>
</table>

</procedure>

</tab>
<tab title="Rules">

<procedure>
<step>Every recursive definition must have one (or more) base cases.</step>
<step>The general case must eventually be reduced to a base case.</step>
<step>The base case stops the recursion.</step>
</procedure>

</tab>
<tab title="Why bother?">

<procedure>

<deflist collapsible="true" default-state="collapsed">
<def title="Can we live without it?">

- yes, you can write “any program” with arrays, loops, and conditionals
</def>
</deflist>

<img src="https://uricsc.github.io/courses/_images/09_s05.png" width="900"/>

<deflist collapsible="true" default-state="collapsed">
<def title="Caveats?">

The choice between a recursive algorithm and an iterative algorithm depends on several factors. Here are some scenarios where a recursive algorithm may be more suitable:

**Problems with inherent recursive structure**

Recursive algorithms are well-suited for solving problems that have a natural recursive structure. If the problem can be easily divided into smaller sub-problems that are of the same type as the original problem, a recursive solution can be intuitive and concise.

**Problems involving backtracking or tree/graph traversal**

Recursive algorithms are commonly used in backtracking scenarios, where you explore different paths or combinations to find a solution. Similarly, tree or graph traversal problems, such as depth-first search or recursive tree traversals, often lend themselves well to recursive solutions.

**Problems with smaller problem sizes**

Recursive algorithms can be more efficient when dealing with smaller problem sizes. If the problem size is relatively small, the overhead of recursive function calls may not significantly impact performance.

**Problems with divide-and-conquer approach**

Recursive algorithms are often employed in divide-and-conquer strategies. If the problem can be divided into independent sub-problems that can be solved individually and then combined to obtain the final result, a recursive approach can be beneficial.

</def>
<def title="Considerations?">
Recursive algorithms may have some drawbacks, such as increased memory usage due to the recursive function call stack, potential performance issues for large problem sizes, and the possibility of exceeding the stack size limit in certain programming languages.

Iterative algorithms can be advantageous in scenarios where a loop structure and mutable variables can be used to iteratively solve the problem without incurring the overhead of recursive function calls.

Ultimately, the choice between recursive and iterative algorithms depends on the nature of the problem, the problem size, the available resources, and the trade-offs between simplicity, efficiency, and readability of the code.
</def>
</deflist>

</procedure>

</tab>
</tabs>

### Recursive Call Tree

<procedure>

<tabs>
<tab title="Largest">

![image](https://1.bp.blogspot.com/-pa9P_k3ONFA/YNRKgBTXLqI/AAAAAAAAMng/CEzvxVrD07g4g-Cz77RBBpGNs4idy9eKQCNcBGAsYHQ/s1920/Blue%2BTeaching%2BMath%2BEducation%2BPresentation.jpg)

<br/>

To find the largest element in `list[a]…list[b]`...  

<br/>

Find the largest element in list[a + 1]...list[b] and call it max b. Compare the elements list[a] and max
- `if (list[a] >= max`) the largest element in `list[a]...list[b]` is `list[a]`
- `else` the largest element in `list[a]...list[b]` is `max`

<br/>

```tex
T(n) =
\begin{cases}
size\ of\ list\ = 1,  & \text{// base case}  \\[2ex]
size\ of\ list\ is\ \gt 1, & \text{// recursive calls}
\end{cases}
```  

<br/><br/>

```c++
int largest (const int list[], int lowerIndex, int upperIndex) {
  int max;
  if (lowerIndex == upperIndex) //size of the sublist is one 
    return list[lowerIndex];
  else {
    max = largest(list, lowerIndex + 1, upperIndex);
    if (list[lowerIndex] >= max) 
      return list[lowerIndex];
    else
      return max;
  }
}
```

</tab>
<tab title="Sum Array">

<br/>

```tex
T(n) =
\begin{cases}
A[0],  & \text{if $n\ = 1$},  & \text{// base case}  \\[2ex]
A[n - 1], & \text{if $n \gt 1$ },  & \text{// recursive calls}
\end{cases}
```

<br/><br/>

``` c++
int sum_array(int *A, int n) {
  //basecase  
  if (n == 1)
    return A[0];

  //solve sub-task
  int sum = sum_array(A, n - 1);

  //return
  return A[n - 1] + sum;
}
```

</tab>
<tab title="Serpinski">

<br/>

```c++
void drawSierpinski(int n, int x, int y) {
    if (n == 0) {
        std::cout << "Drawing triangle at (" << x << ", " << y << ")" << std::endl;
    } else {
        int sideLength = pow(2, n - 1);         // Length of each side of the triangle
        int height = sideLength * sqrt(3) / 2;  // Height of the equilateral triangle

        drawSierpinski(n - 1, x, y);
        drawSierpinski(n - 1, x + sideLength / 2, y);
        drawSierpinski(n - 1, x + sideLength / 4, y + height / 2);
    }
}
```

<br/>

<deflist collapsible="true" default-state="collapsed">
<def title="Structure">

![image](structure.jpeg)
{ thumbnail="true" }

</def>
<def title="Triangle">

![image](triangle.jpeg)
{ thumbnail="true" }

</def>
<def title="Pyramid">

![image](pyramids.jpeg)
{ thumbnail="true" }

</def>
</deflist>

</tab>
<tab title="Binary Search">

<br/>

```c++
int bsearch(int *A, int lo, int hi, int k) {
  //base case
  if (hi < lo)
    return NOT_FOUND;

  // calculate mid point index
  int mid = lo + ( (hi - lo) / 2);
  // key found?
  if (A[mid] == k)
    return mid;
  // key in upper subarray?
  if (A[mid] < k)
    return bsearch(A, mid + 1, hi, k);
  // key is in lower subarray?
  return bsearch(A, lo, mid - 1, k);
}
```

</tab>
</tabs>

</procedure>


## Unimodal Arrays

<procedure>

> Strongly unimodal   
> arrays that can be split into an increasing part followed by a decreasing part

> Weakly unimodal  
> arrays that can be split into a non-decreasing part followed by a non-increasing part 
</procedure>

### Find the max (strongly unimodal)

<procedure>

<deflist collapsible="true" default-state="collapsed">
<def title="No skew">

![image](stronglyUnimodal.jpeg)
{ thumbnail="true" }

</def>
</deflist>

```c++
int max_s_unimodal (int *A, int low, int hi) {  
    if (low == hi)
        return A[low];

int mid = (low + hi) / 2;
    if (A[mid] < A[mid+1])
        return max_s_unimodal(A, mid + 1, hi);
    else
        return max_s_unimodal(A, low, mid);
}
```

<deflist collapsible="true" default-state="collapsed">
<def title="Visualize">

![image](stronglyViz.jpeg)
{ thumbnail="true" }

</def>
</deflist>

</procedure>

### Find the max (weakly unimodal)

<procedure>

<table>
<tr>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Left skew">

![image](leftskew.jpeg)
{ thumbnail="true" }

</def>
</deflist>
</td>
<td>
<deflist collapsible="true" default-state="collapsed">
<def title="Right skew">

![image](rightskew.jpeg)
{ thumbnail="true" }

</def>
</deflist>
</td>
</tr>
</table>

```c++
int max_w_unimodal (int *A, int low, int hi) {
  if (low == hi)
    return A[low];

  int mid = (low + hi) / 2;

  if (A[mid] < A[mid + 1])
    return max_w_unimodal(A, mid + 1, hi);
  else if (A[mid] > A[mid + 1])
    return max_w_unimodal(A, low, mid);
  else {
    int left = max_w_unimodal(A, mid+1, hi);  
    int right = max_w_unimodal(A, low, mid);
    return std::max(left, right);
  }
}
```

<deflist collapsible="true" default-state="collapsed">
<def title="Visualize">

![image](weaklyViz.jpeg)
</def>
</deflist>

</procedure>

## Bimodal Arrays

<procedure>
<deflist collapsible="true" default-state="collapsed">
<def title="Example">

![image](bimodal.jpeg)
</def>
</deflist>

```c++
int bimodalMax(int array[], int start, int end) {
    if (start == end) {
        return array[start];  // Base case: Only one element
    }
    int mid = (start + end) / 2;
    int leftMax = bimodalMax(array, start, mid);   // Maximum in the left sub-array
    int rightMax = bimodalMax(array, mid + 1, end); // Maximum in the right sub-array
    
    return max(leftMax, rightMax);  // Compare and return the maximum of leftMax and rightMax
}
```

</procedure>


## Comparison & Other Modalities

<procedure>

![image](symetricUniBi.jpeg)
{ thumbnail="true" width="900"}
</procedure>


