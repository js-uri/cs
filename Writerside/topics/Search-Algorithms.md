# Search Algorithms

<video src="https://youtu.be/gRK5BUw7TCk" preview-src="search.jpeg" mini-player="true" width="900" />

## Foreshadowing { collapsible="true" default-state="collapsed"}

<procedure>

![sequential v. binary](https://blog.penjee.com/wp-content/uploads/2015/04/binary-and-linear-search-animations.gif)
{width="900"}

</procedure>

## Sequential / Linear Search

<procedure>

![gif](https://www.tutorialspoint.com/data_structures_algorithms/images/linear_search.gif)
{width="900" align="center"}

<br/>

<compare first-title="Pseudo" second-title="C++">

```text

Iterate from 0 to N-1, 
compare the value of every index with x 
if they match, 
    return index
```

```c++
int linearSearch(int array[], int n, int x) {      
    // Going through array sequencially
    for (int i = 0; i < n; i++)
        if (array[i] == x) return i;
    return -1;
}
```
</compare>

**Rules**

- Consider all possible cases
- Find the number of comparisons for each case
- Add the number of comparisons and divide by the number of cases

<table>
<tr>
<td>

```tex
\begin{align}
\text{Best-case} & \Rightarrow T(n) = O(1) \\
& target = A_0 = 1 \ comparison
\end{align}
```

</td>
<td>

```tex
\begin{align}
\text{Worst-case} & \Rightarrow T(n) = O(n) \\
& target = A_{n-1} =  \ comparisons
\end{align}
```

</td>
<td>

```tex
\begin{align}
\text{Average-case} & \Rightarrow T(n) = O(n) \\
& \frac{1 + 2 + 3 + ... + n}{n} = \frac{n(n+1)}{2n} = \frac{n+1}{2} \ comparisons
\end{align}
```

</td>
</tr>
</table>

</procedure>



## Binary Search

<procedure first-title="Iterative" second-title="Recursive">

**Pseudocode**

<tabs>
<tab title="Approaches">

![image](https://1.bp.blogspot.com/-mdUhsP_VnwM/YG8mPKtUc3I/AAAAAAAAATw/ApfeLeeFEoQz_D4Q3xoiXQUNh9u_laJtwCLcBGAsYHQ/w1200-h630-p-k-no-nu/Binary%2BSearch.jpg)

</tab>
<tab title="Iterative">

Consider start index to be at `0` and last index to be `n-1` index at starting
- n -> length
Find middle index `mid` of the array
If `key` is found to be less than `mid` index element then update last index of the array to `mid` - 1
Else if `key` is found to be greater than `mid` index element then update start index of the array to `mid` + 1
Else check for `mid` index element with `key` if not match repeat the above steps til `start` index is less than `end` index

</tab>
<tab title="Recursive">

If `start` is less than `end` perform Binary search else terminate the algorithm.
If the element at `mid` (middle index) is equal to the `key` then return the index as it found the key
Else if the `key` is less than mid (the element middle index) then call the function by passing end as `mid` - 1 (as `key` will be less than `mid` element)
Else if the `key` is greater than mid then call the function by passing start as `mid` + 1 (as `key` will be greater than `mid`)
</tab>
</tabs>

<compare>

```c++
int binarySearchIterative(int array[], int x, int low, int high) {
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (array[mid] == x) return mid;
        if (array[mid] < x) low = mid + 1;
        else high = mid - 1;
    }
    return -1;
}
```

```c++
int binarySearchRecursive(int array[], int x, int low, int high) {
    if (low > high) return -1;
    int mid = low + (high - low) / 2;
    if (array[mid] == x) return mid;
    if (array[mid] < x) return binarySearchRecursive(array, x, mid + 1, high);
    return binarySearchRecursive(array, x, low, mid - 1);
}
```

</compare>

</procedure>

## Analysis

<procedure>

**Rules**

- Break down the problem into sub-problems
- Solve the sub problems
- Merge the sub problems to get desired Output
- *_Note: Must be sorted_*

<table>
<tr>
<td>

```tex
\begin{align}
\text{Best-case} & \Rightarrow T(n) = O(1) \\
& target \ is \ first \ comparison
\end{align}
```

</td>
<td>

```tex
\begin{align}
\text{Worst-case} & \Rightarrow T(n) = O(n) \\
& target \ is \ last \ comparison
\end{align}
```

</td>
<td>

```tex
\begin{align}
\text{Average-case} & \Rightarrow T(n) = O(n) \\
& target \ is \ neither \ first \ nor \ last \ comparison
\end{align}
```

</td>
</tr>
</table>

</procedure>

## Linear vs Binary

<table>
<tr>
<th>Category</th>
<th>Linear Search</th>
<th>Binary Search</th>
</tr>
<tr>
<td>What is it?</td>
<td>Linear search is a method for finding a target value within a list. It sequentially checks each element of the list for the target value until a match is found or until all the elements have been searched.</td>
<td>Binary search is a method for finding a target value within a list. It compares the target value to the middle element of the list; if they are unequal, the half in which the target cannot lie is eliminated and the search continues on the remaining half until it is successful or the remaining half is empty.</td>
</tr>
<tr>
<td>How is it implemented?</td>
<td>Linear search is implemented by looping through the list and checking if the current item is equal to the target value.</td>
<td>Binary search is implemented by comparing the target value to the middle element of the list. If they are unequal, the half in which the target cannot lie is eliminated and the search continues on the remaining half.</td>
</tr>
<tr>
<td>Sorted?</td>
<td>Unsorted lists</td>
<td>Sorted lists</td>
</tr>
<tr>
<td>Time complexity : Best, Worst, Average</td>
<td>O(1), O(n), O(n)</td>
<td>O(1), O(log n), O(log n)</td>
</tr>
<tr>
<td>Space complexity</td>
<td>O(1)</td>
<td>O(1)</td>
</tr>
<tr>
<td>Dimensions</td>
<td>Used on one/multi-dimensional lists</td>
<td>Only used on one-dimensional lists</td>
</tr>
<tr>
<td>Comparisons</td>
<td>Linear search performs equality comparisons. It is used when the list is unsorted because it is inefficient to perform a binary search on an unsorted list.</td>
<td>Binary search performs ordering comparisons. It is used when the list is sorted because it is inefficient to perform a linear search on a sorted list.</td>
</tr>
<tr>
<td>Complexity</td>
<td>Linear search is a simple search algorithm that checks every record until it finds the target value. It is inefficient on large lists.</td>
<td>Binary search is a more complex search algorithm that checks the middle record and eliminates half of the remaining records each time. It is efficient on large lists.</td>
</tr>
<tr>
<td>Applications</td>
<td>Linear search is used in simple applications such as finding an item in a list.</td>
<td>Binary search is used in more complex applications such as finding an item in a sorted list.</td>
</tr>
</table>







