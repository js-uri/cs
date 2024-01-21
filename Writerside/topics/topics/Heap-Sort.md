# Heap Sort

<video src="https://youtu.be/2DmK_H7IdTo?feature=shared" preview-src="heapsort.jpeg" width="900"/>

## What is Heap Sort?

Heap sort is a comparison-based sorting algorithm. It is similar to selection sort where we first find the maximum element and place the maximum element at the end. We repeat the same process for the remaining elements. 

## How does it work?

Heap sort works by first building a heap from the input data. The heap is a binary tree that satisfies the heap property. The heap property states that for every node, the parent node is greater than or equal to the child nodes. 

The heap is created by inserting the elements of the input array one by one into an initially empty heap. After the heap is built, the maximum element is extracted from the heap and placed at the end of the array. The heap is then updated to maintain the heap property. This process is repeated until the heap is empty.

### What is heapify?

Heapify is a procedure that takes an array and a count as input and converts the array into a heap. The heapify procedure is used to build a heap from an array. It is also used to maintain the heap property after an element is removed from the heap.

### What is sift down?

Sift down is a procedure that takes an array, a start index, and an end index as input and moves the element at the start index down the heap until the heap property is satisfied. The sift down procedure is used to maintain the heap property after an element is removed from the heap.

## Pseudocode and Implementation

![image](heapsort2.jpeg)

<tabs>
<tab title="heapsort">

<compare first-title="Pseudo" second-title="C++">

```
procedure heapSort(A : array of items)
    n := length(A)
    heapify(A, n)
    end := n-1
    while end > 0 do
        swap(A[end], A[0])
        end := end - 1
        siftDown(A, 0, end)
end procedure
```

``` c++
void heapSort(int arr[], int n) {
    for (int i = n / 2 - 1; i >= 0; i--)
        heapify(arr, n, i);

    for (int i = n - 1; i >= 0; i--) {
        swap(arr[0], arr[i]);
        heapify(arr, i, 0);
    }
}
```

</compare>

</tab>
<tab title="heapify">

<compare first-title="Pseudo" second-title="C++">

```
procedure heapify(A : array of items, count)
    start := iParent(count-1)
    while start >= 0 do
        siftDown(A, start, count-1)
        start := start - 1
    end while
end procedure
```
``` c++
void heapify(int arr[], int n, int i) {
    int largest = i;
    int l = 2 * i + 1;
    int r = 2 * i + 2;

    if (l < n && arr[l] > arr[largest])
        largest = l;

    if (r < n && arr[r] > arr[largest])
        largest = r;

    if (largest != i) {
        swap(arr[i], arr[largest]);
        heapify(arr, n, largest);
    }
}
```

</compare>
</tab>
<tab title="siftdown">

<compare first-title="Pseudo" second-title="C++">

```
procedure siftDown(A : array of items, start, end)
    root := start
    while iLeftChild(root) <= end do
        child := iLeftChild(root)
        swap := root
        if A[swap] < A[child]
            swap := child
        end if
        if child+1 <= end and A[swap] < A[child+1]
            swap := child + 1
        end if
        if swap = root
            return
        else
            swap(A[root], A[swap])
            root := swap
        end if
    end while
end procedure
```
    
``` c++
void siftdown(int arr[], int start, int end) {
    int root = start;

    while (iLeftChild(root) <= end) {
        int child = iLeftChild(root);
        int swap = root;

        if (arr[swap] < arr[child])
            swap = child;

        if (child + 1 <= end && arr[swap] < arr[child + 1])
            swap = child + 1;

        if (swap == root)
            return;
        else {
            swap(arr[root], arr[swap]);
            root = swap;
        }
    }
}
```

</compare>
</tab>
<tab title="all together">

</tab>
</tabs>


## Time and Space Complexity

- The time complexity of heap sort is O(n log n).
- The space complexity of heap sort is O(1).

## Example

<tabs>
<tab title="Input">

```
[5, 2, 4, 6, 1, 3]
```

</tab>
<tab title="Heapify">

```
[6, 5, 4, 2, 1, 3]
```

</tab>

<tab title="Swap">

```
[3, 5, 4, 2, 1, 6]
```

</tab>

<tab title="Heapify">

```
[5, 3, 4, 2, 1]
```
    
</tab>

<tab title="Swap">

```
[1, 3, 4, 2, 5]
```

</tab>

<tab title="Heapify">

```
[4, 3, 1, 2]
```

</tab>

<tab title="Swap">

```
[2, 3, 1, 4]
```

</tab>

<tab title="Heapify">

```
[3, 2, 1]
```

</tab>

<tab title="Swap">

```
[1, 2, 3]
```

</tab>

<tab title="Heapify">

```
[2, 1]
```

</tab>

<tab title="Swap">

```
[1, 2]
```

</tab>

<tab title="Heapify">

```
[1]
```

</tab>

<tab title="Swap">

```
[1]
```

</tab>

<tab title="Output">

```
[1, 2, 3, 4, 5, 6]
```

</tab>

</tabs>







