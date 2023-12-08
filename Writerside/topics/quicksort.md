# Quick Sort

<video src="https://youtu.be/Hoixgm4-P4M?feature=shared" width="1000" mini-player="true" preview-src="hinh-quicksort.jpg"/>

[GFG | Quick Sort](https://www.geeksforgeeks.org/quick-sort/)

## Definition

Quicksort, also known as partition-exchange sort, is a widely used comparison-based sorting algorithm in computer science. It was developed by Tony Hoare in 1960. Quicksort is known for its efficiency and is often used as the basis for sorting large datasets due to its average and best-case time complexity of `O(n log n)`. The algorithm works by employing a divide-and-conquer strategy and follows these main steps:

<deflist style="full" collapsible="true">
    <def title="Partitioning">
        Quicksort begins by selecting a <b>pivot</b> element from the array. The pivot's choice can vary, but it's typically the first or last element in the array.
    </def>
    <def title="Reordering">
        The elements of the array are then rearranged in such a way that all elements smaller than the pivot are placed to its left, and all elements greater are placed to its right. This step is sometimes called the <b>partitioning</b> step.
    </def>
    <def title="Recursion">
        Quicksort is applied recursively to the subarrays created on the left and right of the pivot, effectively sorting them.
    </def>
    <def title="Combining">
        Once the recursive sorting is complete, the sorted subarrays are combined, and the entire array becomes sorted.
    </def>
</deflist>

## Partitioning

<tabs width="800">
    <tab title="Visual 1">
        <img src="https://blogger.googleusercontent.com/img/a/AVvXsEj_5g_ulJTm7AnqNrfjUt3zYDUi0qf6eepoRqnDvvUhBKIf_vdqP-982F2zX_xV3k1148k8oozojzlBGhKUPrbUshDZs9VMCT0F-iQC8NmV68gDceOu1AIEkl520KEmXgaPXb_R3PdtHNAHhfXHfHDWjQSIpFoKPqC2MIz1Mv50u1XVXI8Gpe2AXu9_3g=s16000" alt="partitioning">
    </tab>
    <tab title="Visual 2">
        <img src="https://www.baeldung.com/wp-content/uploads/sites/4/2021/06/Quicksort-891x1024-1.png" alt="Partitioning">
    </tab>
</tabs>

The efficiency of quicksort is highly dependent on the choice of the pivot element. In the best-case scenario, where the pivot consistently divides the array into nearly equal halves, it achieves its optimal time complexity of `O(n log n)`. However, in the worst-case scenario, where the pivot choice is poor and consistently results in unbalanced partitions, the time complexity can degrade to `O(n^2)`. To mitigate this, various pivot selection strategies, such as selecting the median of three random elements, can be employed to improve its performance.

[//]: # (FIXME : rework link as embeded / iframe)
[//]: # (![dsa](https://opendsa-server.cs.vt.edu/embed/quicksortCON&#41;)

## Pseudo-implementation

<tabs>
    <tab title="quicksort">
        <code-block lang="c++">
        void quicksort(int *A, int n, int m)              
        {
            // shuffle the array  
            std::random_shuffle(A, A + n)
            // call recursive quicksort
            r_quicksort(A, 0, n - 1);
        }
        </code-block>
    </tab>
    <tab title="r_quicksort">
        <code-block lang="c++">
            void r_quicksort(int *A, int lo, int hi)                                           
            {
                if (hi <= lo) return;
                int p = partition(A, lo, hi);
                r_quicksort(A, lo, p - 1);
                r_quicksort(A, p + 1, hi);
            }
        </code-block>
    </tab>
    <tab title="partition">
        <code-block lang="c++" include-lines="0-10">
            int partition (int *A, int lo, int hi)                      
            {
                int i = lo;
                int j = hi + 1;  
                while (1) {
                    // while A[i] < pivot, increase i 
                    while (A[++i] < A[lo])
                        if (i == hi) break;
                    // while A[i] > pivot, decrease j 
                    while (A[lo] < A[--j])
                        if (j == lo) break;
                        // if i and j cross exit theloop
                        if(i >= j) break;
                        // swap A[i] and A[j]
                        std::swap(A[i], A[j]);
                }
                // swap the pivot with A[j]  
                std::swap(A[lo], A[j]);
                //return pivot's position
                return j;
            }
        </code-block>
    </tab>
</tabs>

[//]: # (FIXME : setup embed / iframe)
[//]: # (<iframe width="100%" height="500" src="https://opendsa-server.cs.vt.edu/embed/quicksortAV"></iframe>)

## Analysis : Mathematical & Empirical

[//]: # (FIXME : reconsider use...)
[//]: # ([Analysis of Quick Sort]&#40;https://www.khanacademy.org/computing/computer-science/algorithms/quick-sort/a/analysis-of-quicksort&#41;)

<tabs>
    <tab title="Explanation">
        <video src="https://youtu.be/YQhfIoK8UDY?feature=shared" width="800" mini-player="true" preview-src="quick-sort-diagram.PNG"/>
    </tab>
    <tab title="Worst-case">
        <table>
            <tr>
                <td><b>Visualize</b><br/><img src="https://cdn.kastatic.org/ka-perseus-images/7da2ac32779bef669a6f05decb62f219a9132158.png" alt="quicksort recursion tree | worst-case" width="400"><br/>
                <code-block collapsible="true" collapsed-title="Complexity">
                    c { n + (n-1) + (n-2) + (n-3) + ... 1 }
                        = c * ( {n(n+1)} / {2} ) 
                        = 𝛩(n^2)
                </code-block>
                </td>
                <td>
                    <b>Input sorted, reverse order, equal elements</b><br/>
                    <code-block>
                        T(n) = T(n - 1) + T(0) + 𝛩(n)
                            = T(n - 1) + 𝛩(1) + 𝛩(n)
                            = T(n - 1) + 𝛩(n)
                            = ⋅⋅⋅
                            = 𝛩(n^2)
                    </code-block><br/>
                    can shuffle or <a href="https://youtu.be/HY64dw_Af94">randomize</a> the array (to avoid the worst-case)
                </td>
            </tr>
        </table>
    </tab>
    <tab title="Best-case">
        <table>
            <tr>
                <td><b>Visualize</b><br/><img src="https://cdn.kastatic.org/ka-perseus-images/21cd0d70813845d67fbb11496458214f90ad7cb8.png" alt="quicksort recursion tree | best-case">
                </td>
                <td>
                    <b>Pivot partitions array evenly<br><i>almost never happens</i></b><br/>
                    <code-block>
                        T(n) = 2T( ({n} / {2} ) + 𝛩(n)
                            = ⋅⋅⋅
                            = 𝛩(n log n)
                    </code-block><br/>
                </td>
            </tr>
        </table>
    </tab>
    <tab title="Average-case">
        <table>
            <tr>
                <td><b>Visualize</b><br/><img src="https://cdn-images-1.medium.com/max/600/1*h6C8WodiZvZ04CwgOKOgBA.png" alt="quicksort recursion tree | average-case">
                </td>
                <td>
                    <b>Analysis is more complex</b><br/>
                    <ul>
                        <li>Consider a 9-to-1 proportional split</li>
                        <li>Even a 99-to-1 split yields same running time</li>
                        <li>Faster than merge sort in practice (less data movement)</li>
                    </ul><br>
                    <code-block>
                        T(n) = T( {n}/{10} ) + T( {9n}/{10} ) + 𝛩(n)
                            = ⋅⋅⋅
                            = 𝛩(n log n)
                    </code-block><br>
                    Add all <code>cn</code> from side of tree with greatest depth (right subtree)
                    <br>
                    <code-block>
                        T(n) = cn * log_{ {10}/{9} } n
                             = 𝛩(n log n)
                    </code-block><br/>
                </td>
            </tr>
        </table>
    </tab>
    <tab title="Compared M. Efficiency">
        <table>
            <tr>
                <td></td> <td>Best-Case</td> <td>Average-Case</td> <td>Worst-Case</td> <td>Stable</td> <td>In-place</td>
            </tr>
            <tr>
                <td>Selection Sort</td> <td>n<sup>2</sup></td> <td>n<sup>2</sup></td> <td>n<sup>2</sup></td> <td>no</td> <td>yes</td>
            </tr>
            <tr>
                <td>Insertion Sort</td> <td>n</td> <td>n<sup>2</sup></td> <td>n<sup>2</sup></td> <td>yes</td> <td>yes</td>
            </tr>
            <tr>
                <td>Merge Sort</td> <td>n log n</td> <td>n log n</td> <td>n log n</td> <td>yes</td> <td>no</td>
            </tr>
            <tr>
                <td>Quick Sort</td> <td>n log n</td> <td>n log n</td> <td>n<sup>2</sup></td> <td>no</td> <td>yes</td>
            </tr>
        </table><br/>
        Quicksort's efficiency and simplicity make it a popular choice for sorting algorithms, and it's often used in practice. It's worth noting that while quicksort is typically very efficient, it may not be suitable for certain specialized scenarios where stability or guaranteed worst-case performance is required.
    </tab>
    <tab title="Compared E. Efficiency">
        <img src="12_s16.png" alt="emiprial analysis | running time estimates">
        <a href="https://www.cs.princeton.edu/courses/archive/spring18/cos226/lectures/23Quicksort.pdf">https://www.cs.princeton.edu/courses/archive/spring18/cos226/lectures/23Quicksort.pdf</a>
    </tab>
</tabs>

## Comments on Quick Sort

{style="medium" sorted=""}
Properties
: - benefits substantially from code tuning

Improvements
: use insertion sort for small arrays
: - avoid overhead on small instances (~10 elements) median of 3 elements
: - estimate true median by inspecting 3 random elements [three-way partitioning](https://www.toptal.com/developers/sorting-algorithms/quick-sort-3-way)
: - create three partitions `≤ pivot`, `== pivot`, `≥ pivot`
