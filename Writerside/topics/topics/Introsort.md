# Introsort

## Introsort

Introsort is a hybrid sorting algorithm that provides both fast average performance and (asymptotically) optimal worst-case performance. It begins with quicksort and switches to heapsort when the recursion depth exceeds a level based on (the logarithm of) the number of elements being sorted. This combines the good parts of both algorithms, with practical performance comparable to quicksort on typical data sets and worst-case O(n log n) runtime due to the heap sort.

## How is it used?

Introsort is used in the C++ standard library's `std::sort` function.

## How does it work?

Introsort is a hybrid sorting algorithm that combines the good parts of quicksort and heapsort. It begins with quicksort and switches to heapsort when the recursion depth exceeds a level based on (the logarithm of) the number of elements being sorted. This combines the good parts of both algorithms, with practical performance comparable to quicksort on typical data sets and worst-case O(n log n) runtime due to the heap sort.

## Pseudocode and C++ Example with comments

```c++
// C++ program to implement Introsort
#include <bits/stdc++.h>
using namespace std;

// Function to print an array
void printArray(int arr[], int n)
{
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    cout << "\n";
}

// Function to swap two elements
void swap(int *a, int *b)
{
    int temp = *a;
    *a = *b;
    *b = temp;
}

// Function to return the maximum element from an array
int getMax(int arr[], int n)
{
    int mx = arr[0];
    for (int i = 1; i < n; i++)
        if (arr[i] > mx)
            mx = arr[i];
    return mx;
}

// Function to sort using insertion sort
void insertionSort(int arr[], int left, int right)
{
    for (int i = left + 1; i <= right; i++)
    {
        int temp = arr[i];
        int j = i - 1;
        while (arr[j] > temp && j >= left)
        {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = temp;
    }
}

// Function to sort using selection sort
void selectionSort(int arr[], int left, int right)
{
    for (int i = left; i <= right; i++)
    {
        int min = arr[i];
        int pos = i;
        for (int j = i + 1; j <= right; j++)
        {
            if (arr[j] < min)
            {
                min = arr[j];
                pos = j;
            }
        }
        swap(&arr[pos], &arr[i]);
    }
}

// This function finds an index to partition the array
// It takes the last element as pivot and moves all smaller
// element to left of it and greater elements to right
int partition(int arr[], int low, int high, int pivot)
{
    int i = low;
    while (arr[i] != pivot)
        i++;

    // Move pivot to end
    swap(&arr[i], &arr[high]);

    i = low;
    for (int j = low; j < high; j++)
    {
        if (arr[j] <= pivot)
        {
            swap(&arr[i], &arr[j]);
            i++;
        }
    }
    swap(&arr[i], &arr[high]);
    return i;
}

// This function performs QuickSort on the array
// It takes left and right index of subarray as input
void quickSort(int arr[], int low, int high, int depthLimit)
{
    if (low >= high)
        return;

    // If the depth is less than depthLimit, use Insertion Sort
    if (depthLimit == 0)
    {
        insertionSort(arr, low, high);
        return;
    }

    // If the number of elements in the array is less than 16, use Selection Sort
    if (high - low + 1 <= 16)
    {
        selectionSort(arr, low, high);
        return;
    }

    // Else use QuickSort
    int pivot = getMax(arr + low, high - low + 1);
    int partitionPoint = partition(arr, low, high, pivot);
    quickSort(arr, low, partitionPoint - 1, depthLimit - 1);
    quickSort(arr, partitionPoint + 1, high, depthLimit - 1);
}

// Function to perform Introsort
void introSort(int arr[], int n)
{
    int depthLimit = 2 * log(n);
    quickSort(arr, 0, n - 1, depthLimit);
}

// Driver code
int main()
{
    int arr[] = {2, 5, 3, 1, 4, 8, 6, 7};
    int n = sizeof(arr) / sizeof(arr[0]);
    introSort(arr, n);
    printArray(arr, n);
    return 0;
}
```

Output:

```bash
1 2 3 4 5 6 7 8
```


