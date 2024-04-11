# Randomized Algorithms

<video src="https://www.youtube.com/watch?v=nFw6x7DoYbs&pp=ygUUcmFuZG9taXplZCBhbGdvcml0aG0%3D" preview-src="random_algo.jpeg" width="900" />

## Definition

> Randomized algorithms are algorithms that use random numbers to make decisions. They are used in situations where the input data is too large or complex to be processed by deterministic algorithms. Randomized algorithms are often used in optimization problems, where the goal is to find the best solution from a set of possible solutions.

{ style="note" }

## Key Aspects

<table>
<tr>
<td>

**Randomized Choices**

</td>
<td>

**Randomized Analysis**

</td>
</tr>
<tr>
<td>

Randomized algorithms make random choices during their execution, which can lead to different outcomes each time they are run. These choices are often used to break ties or make decisions when there are multiple options available. 

</td>
<td>

Randomized analysis is a technique used to analyze the performance of randomized algorithms. It involves running the algorithm multiple times with different random inputs and averaging the results to determine the expected performance. This allows us to estimate the running time and space complexity of the algorithm. 

</td>
</tr>
</table>


### Applications & Approaches

<table style="both">
<tr>
<td></td>
<td>

**Monte Carlo Algorithms**

</td>
<td>

**Las Vegas Algorithms**

</td>
</tr>
<tr>
<td>Correctness</td>
<td>

Monte Carlo algorithms are randomized algorithms that have a probabilistic guarantee of correctness. They may produce incorrect results with a small probability, but they are generally fast and efficient.    

</td>
<td>

Las Vegas algorithms are randomized algorithms that always produce the correct result, but their running time may vary. They are often used in situations where correctness is more important than speed.

</td>
</tr>
<tr>
<td>Runtime</td>
<td>

Monte Carlo algorithms have a fixed running time and may produce incorrect results with a small probability. They are often used in situations where speed is more important than correctness.

</td>
<td>

Las Vegas algorithms have a variable running time and always produce the correct result. They are often used in situations where correctness is more important than speed.

</td>
</tr>
<tr>
<td>Efficiency</td>
<td>

Monte Carlo algorithms are generally fast and efficient, but they may produce incorrect results with a small probability. They are often used in situations where speed is more important than correctness.

</td>
<td>

Las Vegas algorithms are generally slower than Monte Carlo algorithms, but they always produce the correct result. They are often used in situations where correctness is more important than speed.

</td>
</tr>
<tr>
<td>Error Analysis</td>
<td>

Monte Carlo algorithms require error analysis to determine the probability of producing incorrect results. This analysis involves running the algorithm multiple times with different random inputs and calculating the probability of error.

</td>
<td>

Las Vegas algorithms do not require error analysis, as they always produce the correct result. However, their running time may vary, so it is important to consider the worst-case scenario when analyzing their performance.

</td>
</tr>
<tr>
<td>Trade-offs</td>
<td>

Monte Carlo algorithms trade correctness for speed, as they may produce incorrect results with a small probability. They are often used in situations where speed is more important than correctness.

</td>
<td>

Las Vegas algorithms trade speed for correctness, as they always produce the correct result but may take longer to do so. They are often used in situations where correctness is more important than speed.

</td>
</tr>
<tr>
<td>Applications</td>
<td>

Monte Carlo algorithms are used in a wide range of applications, including optimization problems, simulation, and statistical analysis. They are particularly useful in situations where speed is more important than correctness.

</td>
<td>

Las Vegas algorithms are used in situations where correctness is more important than speed, such as cryptography, data security, and scientific computing. They are particularly useful in situations where the algorithm must produce the correct result every time.

</td>
</tr>
<tr>
<td>Examples</td>
<td>

Monte Carlo algorithms are used in the field of computational biology to analyze DNA sequences and predict protein structures. They are particularly useful in situations where the algorithm must produce the correct result every time.

</td>
<td>

Las Vegas algorithms are used in the field of cryptography to generate secure encryption keys and protect sensitive data. They are particularly useful in situations where correctness is more important than speed.

</td>
</tr>
</table>

## Advantages & Disadvantages

<table>
<tr>
<td>✅</td>
<td>❌</td>
</tr>
<tr>
<td>can be used to solve complex problems that are difficult to solve with deterministic algorithms</td>
<td>may produce incorrect results with a small probability</td>
</tr>
<tr>
<td>can be more efficient than deterministic algorithms in some cases</td>
<td>may require additional error analysis to determine the probability of producing incorrect results</td>
</tr>
<tr>
<td>can be used in a wide range of applications, including optimization, simulation, and statistical analysis</td>
<td>may be more difficult to implement and analyze than deterministic algorithms</td>
</tr>
<tr>
<td>can provide probabilistic guarantees of correctness in some cases</td>
<td>may be less predictable and reliable than deterministic algorithms</td>
</tr>
<tr>
<td>can be used to generate random numbers and simulate random processes</td>
<td>may require additional computational resources to run multiple times with different random inputs</td>
</tr>
</table>

## Examples

<table style="header-column">
<tr>
<td>

**QuickSort**   

</td>
<td>

QuickSort is a classic example of a randomized algorithm that uses random numbers to sort an array of elements. It works by selecting a random pivot element and partitioning the array into two subarrays based on the pivot. The algorithm then recursively sorts the subarrays until the entire array is sorted.

</td>
</tr>
<tr>
<td>

**Randomized Primality Testing**

</td>
<td>

Randomized primality testing is a technique used to determine whether a given number is prime. It involves running a probabilistic algorithm that uses random numbers to test the primality of the number. The algorithm may produce incorrect results with a small probability, but it is generally fast and efficient.

</td>
</tr>
<tr>
<td>

**Monte Carlo Integration**

</td>
<td>

Monte Carlo integration is a technique used to estimate the value of a definite integral by generating random samples from the function. The algorithm uses random numbers to select points in the function's domain and computes the average value of the function over these points. This allows us to estimate the integral with a high degree of accuracy.

</td>
</tr>
<tr>
<td>

**Las Vegas Sorting**

</td>
<td>

Las Vegas sorting is a technique used to sort an array of elements in random order. The algorithm always produces the correct result, but its running time may vary. It is often used in situations where correctness is more important than speed.

</td>   
</tr>
</table>

<tabs>
<tab title="Monte Carlo Algorithm">

<table>
<tr>
<td>

```c++
#include <iostream>
#include <cstdlib>
#include <ctime>


// Function to generate random numbers
double generateRandomNumber() {
    return (double)rand() / RAND_MAX;
}

// Function to estimate the value of pi using Monte Carlo simulation
double estimatePi(int numPoints) {
    int numPointsInsideCircle = 0;

    for (int i = 0; i < numPoints; i++) {
        double x = generateRandomNumber();
        double y = generateRandomNumber();

        if (x * x + y * y <= 1) {
            numPointsInsideCircle++;
        }
    }

    return 4.0 * numPointsInsideCircle / numPoints;
}

int main() {
    srand(time(0)); // Seed the random number generator

    int numPoints = 1000000;
    double estimatedPi = estimatePi(numPoints);

    std::cout << "Estimated value of pi: " << estimatedPi << std::endl;

    return 0;
}
```

</td>
</tr>
<tr>
<td>

`generateRandomNumber`
: generates a random number between 0 and 1 using the `rand` function.

`estimatePi`
: estimates the value of pi using a Monte Carlo simulation. It generates random points in the unit square and counts the number of points inside the unit circle to estimate the value of pi.

`main`
: seeds the random number generator with the current time, calls the `estimatePi` function with a specified number of points, and prints the estimated value of pi.

</td>
</tr>
</table>

</tab>
<tab title="Las Vegas Sorting">

<table>
<tr>
<td>

```c++
#include <iostream>
#include <vector>
#include <algorithm>
#include <cstdlib>
#include <ctime>

// Function to generate random numbers
int generateRandomNumber() {
    return rand();
}

// Function to perform Las Vegas sorting
void lasVegasSort(std::vector<int>& arr) {
    bool sorted = false;

    while (!sorted) {
        sorted = true;

        for (int i = 0; i < arr.size() - 1; i++) {
            if (arr[i] > arr[i + 1]) {
                std::swap(arr[i], arr[i + 1]);
                sorted = false;
            }
        }
    }
}

int main() {
    srand(time(0)); // Seed the random number generator

    std::vector<int> arr = {5, 2, 8, 1, 3, 7, 4, 6};

    lasVegasSort(arr);

    std::cout << "Sorted array: ";
    for (int num : arr) {
        std::cout << num << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

</td>
</tr>
<tr>
<td>

`generateRandomNumber` 
: generates a random integer using the `rand` function.

`lasVegasSort`
: performs Las Vegas sorting on a vector of integers. It repeatedly iterates through the array and swaps adjacent elements if they are out of order until the array is sorted.

`main`
: seeds the random number generator with the current time, initializes a vector with random integers, calls the `lasVegasSort` function to sort the array, and prints the sorted array.

</td>
</tr>
</table>

</tab>
</tabs>
