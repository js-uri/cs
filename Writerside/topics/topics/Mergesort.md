# Merge Sort

<tabs>
    <tab title="Merge Sort in 4"><video src="https://youtu.be/4VqmGXwpLqc?feature=shared" width="1000" 
mini-player="true" preview-src="Merge-Sort-Algorithm.png"/></tab>
    <tab title="2.7.2. Merge Sort Algorithm"><video src="https://youtu.be/ak-pz7tS5DE?feature=shared" width="1000" mini-player="true" preview-src="mergesort_anime.png"/></tab>
    <tab title="2.7.3 MergeSort in-depth Analysis"><video src="https://youtu.be/mB5HXBb_HY8?feature=shared" width="1000" mini-player="true" preview-src="mergesort_anime.png"/></tab>
    <tab title="Why Is Merge Sort O(n * log(n))?"><video src="https://youtu.be/alJswNJ4P3U?feature=shared" width="1000" mini-player="true" preview-src="mergesort_anime.png"/></tab>
</tabs>

[GFG | Merge Sort](https://www.geeksforgeeks.org/merge-sort/)



## Definition

Mergesort is a widely used and efficient sorting algorithm in computer science. It falls under the category of divide-and-conquer algorithms, which means it breaks down the sorting task into smaller subproblems, solves them, and then combines the results to produce a sorted output.

<img src="https://codeyz.com/wp-content/uploads/2020/07/image-1-792x512.png" alt="divide and conquer technique"/>

<deflist style="full" collapsible="true">
    <def title="Divide">The unsorted array is divided into two equal halves until each subarray contains only one element. This process continues recursively until the base case is reached, where each subarray has a single element, which is trivially sorted.</def>
    <def title="Conquer">After dividing the array, Mergesort sorts the individual elements in each subarray. This is achieved by comparing the elements in the two subarrays and merging them into a new, sorted subarray. The merge operation ensures that the elements are arranged in the correct order.</def>
    <def title="Combine">The merging process continues until the entire array is sorted. The merging is done in a way that it combines the sorted subarrays to create a larger, sorted subarray. This step is repeated until the entire array is sorted.</def>
</deflist>



### Example

- sorting with insertion sort is <code-block lang="tex"> n^2 </code-block>
- we can divide the array into two halves and sort them separately

![image](https://www.kirupa.com/sorts/images/mergesort_1st_div_300.png)

- each sub-problem could be sorted in <code-block lang="tex"> \approx \frac{n^2}{4} </code-block>
- sorting both halves will require <code-block lang="tex"> \approx 2 ( \frac{n^2}{4}) </code-block>
- we need an additional operation to combine both solutions


_Time reduction :_
<code-block lang="tex"> \ \approx n^2 \ \ \ \Rightarrow \ \ \ \approx \bigg(\frac{n^2}{2} \bigg) + n</code-block>



### Divide & Conquer

Consider how this breaks out…

<tabs>
    <tab title="unsorted"><img src="https://www.kirupa.com/sorts/images/mergesort_numbers_300.png" alt=""/></tab>
    <tab title="divide"><img src="https://www.kirupa.com/sorts/images/mergesort_3rd_div_300.png" alt="Division"/></tab>
    <tab title="combine"><img src="https://www.kirupa.com/sorts/images/merge_step_3rd_row_2.png" alt="Step 2"/></tab>
    <tab title="sorted"><img src="https://www.kirupa.com/sorts/images/everything_sorted_merge_300.png" alt="Sort Complete"/></tab>
    <tab title="try it">
        <a href="https://opendsa-server.cs.vt.edu/embed/mergesortAV">mergesortAV</a>
        <br/>
        <ul>
            <li>Add the collection values to <i>Your Values</i><br/><code-block lang="tex"> Collection\ values = [5,
12, 4,1, 2,8, 2, 6,10]</code-block></li>
            <li>Change the <i>List Size</i> to <i>9</i></li>
            <li>Press <kbd>run</kbd> and click through the steps...</li>
        </ul>
        <br/>
        <a href="https://opendsa-server.cs.vt.edu/embed/mergesortCON">Visualize</a>
    </tab>
</tabs>



### Merging two sorted arrays

[Merging two sorted arrays](https://www.geeksforgeeks.org/merge-two-sorted-arrays/)

![](https://www.baeldung.com/wp-content/uploads/2019/12/Merge-Sorted-Arrays.png){width="800"}

*_to guarantee a_* **[lineartime](https://www.khanacademy.org/computing/computer-science/algorithms/merge-sort/a/linear-time-merging)** *_operation_*



## Pseudo-implementation

<tabs>
    <tab title="overall">
        <code-block lang="c++">
        MergeSort(arr[], lo,  hi) {
            if (hi ≤ lo) return;
            // Find the middle point to divide the array into two halves:
            int mid = lo + (hi - lo) / 2;
            // Call mergeSort for first half:
            mergesort(A, lo, mid);
            // Call mergeSort for second half:
            mergesort(A, mid + 1, hi);
            // Merge the two halves sorted in steps 2 and 3:
            merge(A, lo, mid, hi);
        }
        </code-block>
        <br/>
        <img src="https://algs4.cs.princeton.edu/22mergesort/images/mergesort-overview.png" alt="sort two halves"/>
    </tab>
    <tab title="mergesort">
        <code-block lang="c++">
            void mergesort(int *A, int n) {
                int *aux = new int[n];  
                r_mergesort(A, aux, 0, n - 1);
                delete[] aux;
            }
        </code-block>
    </tab>
    <tab title="r_mergesort">
        <code-block lang="c++">
            void r_mergesort(int *A, int *aux, int lo,int hi) {
                //basecase(single element or empty list)
                if (hi ≤ lo) return;
                //divide
                int mid = lo + (hi - lo) / 2;
                //recursively sort halves  
                r_mergesort(A, aux, lo, mid);
                r_mergesort(A, aux, mid + 1, hi);
                //merge results
                merge(A, aux, lo, mid, hi);
            }
        </code-block>
    </tab>
    <tab title="merge">
        <code-block lang="c++">
            void merge (int *A, int *aux, int lo, int mid, int hi) {
                // copy array
                std::memcpy(aux + lo, A + lo, (hi - lo + 1 * sizeof(A)));
                // merge 
                int i = lo, j = mid + 1;
                for (int k = lo; k &le; hi; k++) {
                    if (i &gt; mid) A[k] = aux[j++];
                    else if (j &gt; hi) A[k] = aux[i++];
                    else if(aux[j] &lt; aux[i]) A[k] = aux[j++];
                    else A[k] = aux[i++];
                }
            }
        </code-block>
    </tab>
    <tab title="a[] and aux[]"><img src="https://algs4.cs.princeton.edu/22mergesort/images/merge.png" alt="algs4.cs.princeton.edu | 
mergesort"/></tab>
    <tab title="top-down trace"><img src="https://algs4.cs.princeton.edu/22mergesort/images/mergesortTD-bars.png" alt="algs4.cs.princeton.
edu | mergesortTD-bars"/></tab>
</tabs>



## Analysis : Mathematical & Empirical

[Analysis (recurrence)](https://www.khanacademy.org/computing/computer-science/algorithms/merge-sort/a/analysis-of-merge-sort)



### Complexities

<table>
    <tr>
    <td></td><td>Worst-case</td><td>Best-case</td><td>Average-case</td>
    </tr>
    <tr>
        <td>Merge Sort</td> <td><code-block lang="tex"> n\ log\ n</code-block></td> 
        <td><code-block lang="tex"> n\ log\ n</code-block></td> 
        <td><code-block lang="tex"> n\ log\ n</code-block></td>
    </tr>
</table>


#### Breakdown (generalization)

A merge sort consists of several passes over the input.

<deflist style="medium">
    <def title="1st Pass">
        merges segments of size : <code-block lang="tex"> 1</code-block>
    </def>
    <def title="2nd Pass">
        merges segments of size : <code-block lang="tex"> 2</code-block>
    </def>
    <def title="i-th Pass">
        merges segments of size : <code-block lang="tex"> 2^{i-1}</code-block>
    </def>
    <def title="Total number of passes">
        <code-block lang="tex"> log\ n</code-block>
    </def>
</deflist>

As merge showed, we can merge two sorted segments in linear time, which means that each pass takes
<code-block lang="tex">O(n)\ time</code-block> 
Since there are <code-block lang="tex"> log\ n\ passes</code-block>
 total computing time is 
<code-block lang="tex"> 𝛩(n\ log\ n)</code-block>
or expressed as: <code-block lang="tex"> T(n) = 2T ( n/2 ) + \Theta(n)</code-block>



### Recursion Tree

[Recursion Tree (trace)](https://youtu.be/C4JjXc0htp0)

<img src="https://www.kirupa.com/sorts/images/running_complexity_300.png" alt="" width="400"/>

<deflist collapsible="true">
    <def title="trace" collapsible="true" default-state="collapsed">
        <img src="https://media.geeksforgeeks.org/wp-content/uploads/20220722205737/MergeSortTutorial.png" alt=""/>
    </def>
    <def title="time" collapsible="false" default-state="expanded">
        Total time for <code>mergeSort</code> is the sum of the merging times for all the levels
        <list style="bullet">
            <li>If there are <code>l</code> levels in the tree, then the total merging time is <code-block lang="tex"> l * cn</code-block></li>
            <li>Where <code>l</code> is the number of subproblem levels until subproblems reach size <code>n</code></li>
            <li>For total time, we end up with: <code-block lang="tex"> cn (log\ n + 1)</code-block></li>
            <li>Discard the lower-order term (constant) and the coefficient:<code-block lang="tex"> \Theta(n\ 
log\ n)
</code-block></li>
        </list>
    </def>
</deflist>

[Visualize](https://opendsa-server.cs.vt.edu/embed/MergeSortAnalysisCON)



## Comments on Merge Sort

<table>
<tr>
<td>Advantages</td>
<td>Disadvantages</td>
</tr>
<tr>
<td>
    <list style="bullet">
        <li>relatively efficient for sorting large datasets</li>
        <li><b>stable sort</b> : the order of elements with equal values is preserved during the sort</li>
        <li>easy to implement</li>
        <li>useful for external sorting</li>
        <li>requires relatively few additional resources (such as memory)</li>
    </list>
</td>
<td>
    <list style="bullet">
        <li>slower compared to the other sort algorithms for smaller tasks</li>
        <li>requires an additional memory space of 0(n) for the temporary array</li>
        <li>regardless of sort status, goes through whole process</li>
        <li>requires more code to implement</li>
    </list>
</td>
</tr>
</table>



### Consider

**Think about reversing an array or string**

<deflist collapsible="true">
    <def title="Solution 1" collapsible="true" default-state="collapsed">
        <b>Use an additional array of equal size</b>
        <list>
            <li>what is the required extra memory?</li>
        </list>
    </def>
    <def title="Solution 2" collapsible="true" default-state="collapsed">
        <b>Exchange first and last and work recursively on the inner part</b>
        <list>
            <li>can do it iteratively, as well</li>
            <li>what is the required extra memory?</li>
        </list>
    </def>
</deflist>



## In-place Sorting

<note>
    An algorithm does not use extra space for manipulating the input but may require a small though non-constant 
extra space for its operation. Usually, this space is <code-block lang="tex"> O(log\ n)</code-block>
Though sometimes anything in <code-block lang="tex"> O(n)</code-block> (Smaller than linear) is allowed.
    <a href="https://www.geeksforgeeks.org/in-place-algorithm/">GFG | In-place Algorithms</a>
</note>

<table>
<tr>
<td width="700">Selection Sort</td>
</tr>
<tr>
<td>
<code-block lang="c++">
void selectionSort(int arr[], int n)
{
    int i, j, min_idx;
    // One by one move boundary of unsorted subarray
    for (i = 0; i &lt; n-1; i++) {
        // Find the minimum element in unsorted 
        // array
        min_idx = i;
        for (j = i + 1; j &lt; n; j++)
            if (arr[j] &lt;[min_idx]) min_idx = j;
        // Swap the found minimum element with 
        // the first element
        if(min_idx != i)
            swap(&amp;arr[min_idx], &amp;arr[i]);
    }
}
</code-block>
</td>
</tr>
<tr>
<td><deflist collapsible="true">
    <def title="In-place?" collapsible="true"  default-state="collapsed">
        <b>Yes</b>; it does not require extra space.
    </def>
</deflist></td>
</tr>
</table>

<table>
<tr>
<td width="700">Insertion Sort</td>
</tr>
<tr>
<td><code-block lang="c++">
void insertionSort(int arr[], int n) 
{ 
    int i, key, j;
    for (i = 1; i &lt; n; i++) 
    { 
        key = arr[i]; 
        j = i - 1;
        // Move elements of arr[0..i-1], 
        // greater than key, to one position 
        // ahead of their current position
        while (j >= 0 &amp;&amp; arr[j] &gt; key)
        { 
            arr[j + 1] = arr[j]; 
            j = j - 1; 
        } 
        arr[j + 1] = key; 
    } 
}
</code-block></td>
</tr>
<tr>
<td><deflist collapsible="true">
    <def title="In-place?" collapsible="true" default-state="collapsed">
        <b>Yes</b>; it does not require extra space.
    </def>
</deflist></td>
</tr>
</table>



## Stable Sorting

<note>
    <img src="https://media.geeksforgeeks.org/wp-content/uploads/20220825145858/del.png" alt=""/>
    <p>
        A sorting algorithm is said to be stable if two objects with equal keys appear in the same order in sorted output as they appear in the input data set
    </p>
    <a href="https://www.geeksforgeeks.org/stable-and-unstable-sorting-algorithms/">GFG | Stable and Unstable Sorting Algorithms</a>
</note>

<tabs>
    <tab title="Stable?">
        <table>
        <tr>
        <td><img src="11_s20_1.png" alt=""/></td>
        <td><img src="11_s20_2.png" alt=""/></td>
        </tr>
        <tr>
        <td colspan="2">
            <deflist collapsible="true">
                <def title="In-place?" collapsible="true" default-state="collapsed">
                    <warning><p>NOT STABLE</p></warning>
                </def>
            </deflist>
        </td>
        </tr>
        </table>
    </tab>
    <tab title="Stable?">
        <table>
        <tr>
        <td width="50%"><img src="11_s20_1.png" alt=""/></td>
        <td><img src="11_s20_3.png" alt=""/></td>
        </tr>
        <tr>
        <td colspan="2">
            <deflist collapsible="true">
                <def title="Stable?" collapsible="true" default-state="collapsed">
                    <note><p>STABLE</p></note>
                </def>
            </deflist>
        </td>
        </tr>
        </table>
    </tab>
</tabs>



### Stability

<deflist style="full" collapsible="true">
    <def title="Consider..." default-state="expanded">
        <list>
            <li>long distance swaps</li>
            <li>try: <code-block lang="tex"> [5, 2, 3, 8, 4, 5, 6]</code-block></li>
        </list>
    </def>
    <def title="Is selection sort stable?" collapsible="true" default-state="collapsed">
        Selection sort algorithm picks the minimum and swaps it with the element at current position.
        <br/>
        Suppose the array is:
        <br/>
        <code-block lang="tex"> [5, 2, 3, 8, 4, 5, 6] \Rightarrow [5a, 2, 3, 8, 4, 5b, 6] </code-block>
        <br/>
        <list>
            <li>After first iteration : 2 will be swapped with the element in 1st position<br/>So our array =>  
<code-block lang="tex"> [2, 5a, 3, 8, 4, 5b, 6]</code-block></li>
            <li>Once the array is in sorted order <code-block lang="tex"> [2, 3, 4, 5b, 5a, 6, 8]</code-block> and we 
clearly 
see that 
<code-block lang="tex"> 5a</code-block> comes before <code-block lang="tex"> 5a</code-block> in initial array but 
not in 
the sorted array.</li>
            <li>Therefore, selection sort is <b>NOT STABLE</b>.</li>
        </list>
    </def>
</deflist>

<deflist style="full" collapsible="true">
    <def title="Consider..." default-state="expanded">
        <list>
            <li>equal items never pass each other <i>(depends on correct implementation)</i></li>
        </list>
    </def>
    <def title="Is insertion sort stable?" collapsible="true" default-state="collapsed">
        <list>
            <li>Therefore, selection sort is <b>STABLE</b>.</li>
        </list>
    </def>
</deflist>



## Complexity

<table>
    <tr>
        <td></td> <td>Best-Case</td> <td>Average-Case</td> <td>Worst-Case</td> <td>Stable</td> <td>In-place</td>
    </tr>
    <tr>
        <td>Selection Sort</td> 
        <td>
            <code-block lang="tex">
                n^2
            </code-block>
        </td>
        <td>
            <code-block lang="tex">
                n^2
            </code-block>
        </td>
        <td>
            <code-block lang="tex">
                n^2
            </code-block>
        </td>
        <td>
            <code-block lang="tex">
                no
            </code-block>
        </td>
        <td>
            <code-block lang="tex">
                yes
            </code-block>
        </td>
    </tr>
    <tr>
        <td>Insertion Sort</td>
        <td>
            <code-block lang="tex">
                n
            </code-block>
        </td>
        <td>
            <code-block lang="tex">
                n^2
            </code-block>
        </td>
        <td>
            <code-block lang="tex">
                n^2
            </code-block>
        </td>
        <td>
            <code-block lang="tex">
                yes
            </code-block>
        </td>
        <td>
            <code-block lang="tex">
                yes
            </code-block>
        </td>
    </tr>
    <tr>
        <td>Merge Sort</td>
        <td>
            <code-block lang="tex">
                n\ log\ n
            </code-block>
        </td>
        <td>
            <code-block lang="tex">
                n\ log\ n
            </code-block>
        </td>
        <td>
            <code-block lang="tex">
                n\ log\ n
            </code-block>
        </td>
        <td>
            <code-block lang="tex">
                yes
            </code-block>
        </td>
        <td>
            <code-block lang="tex">
                no
            </code-block>
        </td>
    </tr>
</table>