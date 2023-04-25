# Selection Sort

Selection sort is a simple sorting algorithm that works by repeatedly finding the minimum element from the unsorted part of an array and putting it at the beginning of the array. This process is then repeated for the remaining unsorted part of the array until the entire array is sorted.

The step-by-step process for selection sort is given below:

1. Find the minimum element in the unsorted part of the array.
2. Swap the minimum element with the first element in the unsorted part of the array.
3. Move the boundary of the sorted part of the array one position to the right.
4. Repeat steps 1-3 until the entire array is sorted.

Selection Sort can be represented as follows:

![Representation of Selection Sort](https://he-s3.s3.amazonaws.com/media/uploads/2888f5b.png)

Selection Sort can be implemented in C as follows:

```
void selection_sort(int arr[], int n) {
    int i, j, min_idx;

    // One by one move boundary of unsorted subarray
    for (i = 0; i < n-1; i++) {
        // Find the minimum element in unsorted array
        min_idx = i;
        for (j = i+1; j < n; j++) {
            if (arr[j] < arr[min_idx])
                min_idx = j;
        }
        // Swap the found minimum element with the first element
        int temp = arr[min_idx];
        arr[min_idx] = arr[i];
        arr[i] = temp;
    }
}
```

In this implementation, the function selection_sort takes an integer array arr and its size n as input arguments. The outer loop iterates through the array, while the inner loop finds the minimum element in the unsorted part of the array. The minimum element is then swapped with the first element in the unsorted part of the array, and the boundary of the sorted part of the array is moved one position to the right. The process is repeated until the entire array is sorted.

The function written above can be called as shown below:

```
int arr[] = {64, 25, 12, 22, 11};
int n = sizeof(arr)/sizeof(arr[0]);
selection_sort(arr, n);
```

After the function call, the arr array will be sorted in ascending order.


The program in this repository demonstrates an implementation of Selection Sort in C.

### Code:

```
// implementing selection sort

#include <stdio.h>

void SelectionSort(int a[], int n);

int main()
{
    int arr[5] = {56, 17, 9, 32, 7};
    int i;

    printf("Available array:\n");

    for(i = 0; i < 5; i++)
    {
        printf("%d ", arr[i]);
    }

    printf("\n\n");

    // sorting the given array
    SelectionSort(arr, 5);

    printf("Sorted array (Selection Sort):\n");

    for(i = 0; i < 5; i++)
    {
        printf("%d ", arr[i]);
    }

    return 0;
}


// selection sort
void SelectionSort(int a[], int n)
{
    int smallest_index;
    int temp;
    int i, j;

    for(i = 0; i < n - 1; i++)
    {
        // storing the smallest index in the variable named 'smallest' (assumed to be 1)
        smallest_index = i;

        for(j = i + 1; j < n; j++)
        {
            // checking the element at the index after i; if smaller than smallest then smallest index = index of next element
            if(a[smallest_index] > a[j])
            {
                smallest_index = j;
            }
        }

        // if the smallest element is not at index i, switching the two index values
        if(i != smallest_index)
        {
            temp = a[i];
            a[i] = a[smallest_index];
            a[smallest_index] = temp;
        }
    }
}
```

### Output:

![selectionSort.c output](https://github.com/Aditi-exe/C-Selection-Sort/blob/main/selectionSort.png)

