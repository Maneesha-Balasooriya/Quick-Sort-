# Quick-Sort-
Quick Sort  Using recurtion


import java.util.Arrays;

public class QuickSort {
    // Quick Sort function
    public static void quickSort(int[] arr, int low, int high) {
        if (low < high) {
            // Partition the array
            int pivotIndex = partition(arr, low, high);

            // Recursively sort elements before and after partition
            quickSort(arr, low, pivotIndex - 1);
            quickSort(arr, pivotIndex + 1, high);
        }
    }

    // Partition function to place pivot in the correct position
    private static int partition(int[] arr, int low, int high) {
        int pivot = arr[high];  // Choosing last element as pivot
        int i = low - 1; // Index for smaller element

        for (int j = low; j < high; j++) {
            // If current element is smaller than pivot, swap it
            if (arr[j] < pivot) {
                i++;
                swap(arr, i, j);
            }
        }

        // Swap the pivot with the element at i+1
        swap(arr, i + 1, high);
        return i + 1; // Return the partition index
    }

    // Swap function to swap two elements in the array
    private static void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

    // Main function to test Quick Sort
    public static void main(String[] args) {
        int[] arr = {10, 7, 8, 9, 1, 5};
        System.out.println("Original Array: " + Arrays.toString(arr));

        quickSort(arr, 0, arr.length - 1);
        
        System.out.println("Sorted Array: " + Arrays.toString(arr));
    }
}
