# Sorting Algorithms

## Internships &amp; Jobs { collapsible="true" }

<table style="none">
<tr>
<td><a href="https://www.google.com/about/careers/applications/how-we-hire"><img src="https://www.seocoburg.com/wp-content/uploads/2017/08/google-logo-e1503999999491.png" alt="image" /></a></td>
<td><a href="https://www.amazon.jobs/en/landing_pages/software-development-topics"><img src="https://i.pinimg.com/originals/07/35/8f/07358ffe50bd4483b62290a568ad3a61.png" alt="image" /></a></td>
</tr>
<tr>
<td><a href="https://www.metacareers.com/life/"><img src="https://cdn.comparably.com/27416063/l/7642_logo_meta-75510.png" alt="image" /></a></td>
<td><a href="https://uri.joinhandshake.com/login"><img src="https://www.insidehighered.com/sites/default/files/media/handshakelogo.PNG" alt="image" /></a></td>
</tr>
</table>

## Overview

<table>
<tr>
<td>

<procedure>
<b>Warm-up 1</b>
<p>Analyze this code</p>

<br/>

```c++
unsigned int argmin (const std::vector<int> &values) { 
    unsigned int length = values.size();
    assert(length > 0);
    unsigned int idx = 0;
    int current = values[0];
    for (unsigned int i = 1; i < length; i++) {
        if (values[i] < current) {
            current = values[i];
            idx = i;
        }
    }
    return idx;
}
```

<br/>

```tex
\text{T(n) = ?}
```

<deflist collapsible="true" default-state="collapsed">
<def title="Based on the number of comparisons...">

```tex
\text{T(n) = n - 1}
```

The number of comparisons in this program is `n - 1`, where n is the size of the vector.

</def>
</deflist>

</procedure>
</td>
<td>

<procedure>
<b>Warm-up 2</b>
<p>Analyze this code</p>

<br/>

```c++
bool argk (const std::vector<int> &values, int k, unsigned int &idx) 
{  
    unsigned int length = values.size();
    for (unsigned int i = 0; i < length; i++) {
        if (values[i] == k) {
            idx = i;
            return true;
        }
    }
    return false;
}
```

<br/>

```tex
\text{T(n) = ?}
```

<deflist collapsible="true" default-state="collapsed">
<def title="Based on the number of comparisons...">

```tex
\text{T(n) = n}
```

The number of comparisons in this program is equal to the number of elements in the given vector. Therefore, the number of comparisons is dependent on the size of the input vector. The time complexity of this program is `O(n)`, where `n` is the size of the input vector.

</def>
</deflist>

</procedure>
</td>
</tr>
</table>

### Types of Analysis

<table>
<tr>
<td colspan="2">

<deflist collapsible="true">
<def title="Worst-case ☹️">
<p>Worst-case analysis is the most common type of analysis. It is used to determine the upper bound on the running time of an algorithm. It is also used to determine the lower bound on the running time of an algorithm.</p>
<p>Worst-case analysis is used to determine the worst-case running time of an algorithm. It is also used to determine the worst-case running time of an algorithm.</p>
</def>
</deflist>
</td>
<td colspan="2">
<deflist collapsible="true">
<def title="Average-case 🙂">
<p>Average-case analysis is used to determine the average-case running time of an algorithm. It is also used to determine the average-case running time of an algorithm.</p>
</def>
</deflist>
</td>
<td colspan="2">
<deflist collapsible="true">
<def title="Best-case 🦄">
<p>Best-case analysis is used to determine the best-case running time of an algorithm. It is also used to determine the best-case running time of an algorithm.</p>
</def>
</deflist>
</td>
</tr>
<tr>
<td colspan="3">
<tip>
<procedure>

```tex
\text{While asymptotic analysis describes } T(n) \Rightarrow \infty \\
```

<step>

```tex
\text{asymptotic notation: } Big-O, Big-\Omega, and\ \Theta
```
</step>
</procedure>
</tip>
</td>
<td colspan="3">
<tip>
<procedure>

```tex
\text{Case analysis looks into the different input types} \\
```

<step>

```tex
\text{best-case, worst-case, average-case}
```
</step>
</procedure>
</tip>
</td>
</tr>
</table>

#### Examples

<procedure>

<a href="https://www.geeksforgeeks.org/program-for-factorial-of-a-number/"><b>Factorial of a number (iterative algorithm)</b></a>

```text
function factorial(n):
    if n <= 1:
        return 1
    result = 1
    for i in range(1, n+1):
        result *= i
    return result
```

<br/>

```text
?? Case

Best-case:
Without possibility of extra steps, the only analysis can be best-case…
```
{ collapsible="true" }



<a href="https://www.geeksforgeeks.org/linear-search/"><b>Sequential search (return first occurrence)</b></a>

```text
function find_first(items, target):
    index = 0
    while index < len(items):
        if items[index] == target:
            return index
        index += 1
    return -1
```

<br/>

```text
?? Case

Average-case:
Arguably, the first occurrence could be the first or last element/node in the collection. The majority of the time, it will not be either first or last, leading to only one logical result, average-case…
```
{ collapsible="true" }



<a href="https://www.geeksforgeeks.org/linear-search"><b>Sequential search (return last occurrence)</b></a>

```text
function find_last(items, target):
    index = len(items) - 1
    while index >= 0:
        if items[index] == target:
            return index
        index -= 1
    return -1
```

<br/>

```text
?? Case

Worst-case:
Arguably, the value could be found at anywhere but the last element/node of the collection. However, we must still complete a comparison of the desired value and each element/node in the collection to exhaust all possibilities, therefore, it would fall into worst-case…
```
{ collapsible="true" }

</procedure>


## Basic Sorting

<b>Given <code>n</code> elements that can be compared according to a <a href="https://math.libretexts.org/Bookshelves/Combinatorics_and_Discrete_Mathematics/A_Spiral_Workbook_for_Discrete_Mathematics_(Kwong)/07%3A_Relations/7.04%3A_Partial_and_Total_Ordering">total order</a> relation</b>

<procedure style="choices">
<p>we want to rearrange them in non-increasing/non-decreasing order</p>
<p>for example (non-decreasing):</p>
<step>
<shortcut>input</shortcut> : sequence of items 
<code-block lang="tex"> A = [k_0, k_1, k_2, \dots, k_{n-1}]</code-block>
</step>
<step>
<shortcut>output</shortcut> : permutation of <code>A</code> 
<code-block lang="tex"> B \ \ \ | \ \ \ B[0] \le B[1] \le B[2] \le \dots B[n-1]</code-block>
</step>
</procedure>

<i>Central problem in computer science...</i>



### Insertion Sort

<procedure>

![Insertion Sort](https://markbowman.org/LCC/SortInsertion.gif)

**Array is divided into sorted and unsorted parts**
- algorithm scans array from left to right

**Invariants**
- left side of array is sorted
- right side of array is unsorted

</procedure>

#### Building your own Insertion Sort

<procedure>

![Insertion Sort](https://www.educba.com/academy/wp-content/uploads/2019/11/Insertion-Sort-in-JavaScript.png)
{ thumbnail="true" }

```text
procedure insertionSort(A : array of items)
    int n := length(A)
    for i = 1 to n - 1 do
        int j := i
        while j > 0 and A[j-1] > A[j] do
            swap A[j] and A[j-1]
            j := j - 1
        end while
    end for
end procedure
```

</procedure>

#### Analysis of Comparisons

<table>
<tr>
<td>
<procedure>

**Worst-case?**

- input is already sorted in descending order

```tex
\begin{align}
\sum^{N-1}_{i-1} i\ &= 1 + 2 + 3 + \dots + N-1 \\
&= \frac{N(N-1)}{2} \\
&= \frac{N^2}{2} - \frac{N}{2} \\
&\approx \frac{N^2}{2}  \\
&= O(N^2)  \\
\end{align}
```
</procedure>
</td>
<td>
<procedure>

**Average-case?**

- input is randomly ordered

```tex
\begin{align}
\sum^{N-1}_{i-1} \frac{i}{2} &= \frac{1}{2}(1 + 2 + 3 + \dots + (N-1)) \\
&= \frac{N(N-1)}{4} \\
&= \frac{N^2}{4} - \frac{N}{4} \\
&\approx \frac{N^2}{4}  \\
&= O(N^2)  \\
\end{align}
```
</procedure>
</td>
<td></td>
</tr>
</table>







### Selection Sort

<procedure>

![Selection Sort](https://markbowman.org/LCC/SortSelection.gif)

**Array is divided into sorted and unsorted parts**
- algorithm scans array from left to right
- algorithm finds the smallest element in the unsorted part
- algorithm swaps the smallest element with the first element in the unsorted part
- algorithm repeats until the array is sorted

**Invariants**
- left side of array is sorted
- right side of array is unsorted
- smallest element in unsorted part is 
  - at the beginning of the unsorted part
  - greater than the largest element in the sorted part
  - less than all other elements in the unsorted part
  - less than all other elements in the sorted part

</procedure>

#### Building your own Selection Sort

<procedure>

![Selection Sort](sorts1.jpeg)
{ thumbnail="true" }

```text
procedure selectionSort(A : array of items)
    int n := length(A)
    for i = 0 to n - 1 do
        int min := i
        for j = i + 1 to n - 1 do
            if A[j] < A[min] then
                min := j
            end if
        end for
        swap A[i] and A[min]
    end for
end procedure
```

</procedure>

### Time Complexity of Basic Sorting Algorithms

```tex
\begin{array}{lclclclclcl}
\hline
\textbf{Algorithm} & \textbf{Worst Case} & \textbf{Avg Case} & \textbf{Best Case} \\
\hline
\text{Insertion Sort} & \mathcal{O}(n^2) & \mathcal{O}(n^2) & \mathcal{O}(n) \\
\hline
\text{Selection Sort} & \mathcal{O}(n^2) & \mathcal{O}(n^2) & \mathcal{O}(n^2) \\
\hline
\end{array}
```

