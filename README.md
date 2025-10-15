This project includes basic implementations of four sorting algorithms: Bubble Sort, Quick Sort, Insertion Sort, and Selection Sort.

Bubble Sort works by repeatedly swapping adjacent elements if they are in the wrong order. It’s simple but not very efficient, especially for large lists. It has a best-case time complexity of O(n) (when the list is already sorted), but in the average and worst cases, it takes O(n²) time.

for i from 0 to length of array - 1
    for j from 0 to length of array - i - 2
        if array[j] > array[j + 1]
            swap array[j] and array[j + 1]

Quick Sort is a faster, divide-and-conquer algorithm. It picks a pivot element and splits the list into smaller parts, then sorts them recursively. Its average and best-case time complexity is O(n log n), but the worst case can be O(n²), depending on the pivot choice.

function quickSort(array, low, high)
    if low < high
        pivotIndex = partition(array, low, high)
        quickSort(array, low, pivotIndex - 1)
        quickSort(array, pivotIndex + 1, high)

function partition(array, low, high)
    pivot = array[high]
    i = low - 1
    for j from low to high - 1
        if array[j] < pivot
            i = i + 1
            swap array[i] and array[j]
    swap array[i + 1] and array[high]
    return i + 1
Insertion Sort goes through each element and inserts it into its correct position in the already sorted part of the list. It’s good for small or nearly sorted lists, with a best-case time complexity of O(n), but in most cases, it takes O(n²) time.

for i from 1 to length of array - 1
    key = array[i]
    j = i - 1
    while j >= 0 and array[j] > key
        array[j + 1] = array[j]
        j = j - 1
    array[j + 1] = key
Selection Sort works by finding the smallest element from the unsorted part and placing it at the beginning. It’s also easy to understand but not very efficient, taking O(n²) time in all cases.

for i from 0 to length of array - 1
    minIndex = i
    for j from i + 1 to length of array - 1
        if array[j] < array[minIndex]
            minIndex = j
    swap array[i] and array[minIndex]
Among these, Quick Sort is usually the most efficient, especially for larger datasets, because of its average time complexity of O(n log n). For smaller or nearly sorted lists, Insertion Sort can be a good choice. Bubble Sort and Selection Sort are generally slower and not used in real-world applications, but they are useful for learning the basics of sorting.
