### Selection sort is a simple sorting algorithm that works by repeatedly finding the minimum (or maximum, depending on sorting order) element from the unsorted part of the array and swapping it with the element at the beginning of the unsorted part. Here's a step-by-step explanation of how selection sort works:

1. **Concept**: The idea behind selection sort is to divide the array into two parts: sorted and unsorted. Initially, the entire array is considered unsorted.

2. **Finding the Minimum**: In each iteration of selection sort, it finds the smallest element in the unsorted part of the array.

3. **Swapping**: Once the smallest element is found, it is swapped with the leftmost unsorted element (which becomes a part of the sorted array).

4. **Advancing the Boundaries**: After each iteration, the boundary between the sorted and unsorted parts is moved one element to the right. This means the sorted part grows incrementally, and the unsorted part shrinks until the entire array is sorted.

5. **Algorithm Steps**:

- Find the smallest element in the unsorted array.
- Swap it with the element at the beginning of the unsorted array.
- Expand the boundary of the sorted array to include this newly swapped element.
- Repeat until the entire array is sorted.
6. **Efficiency**: Selection sort is not very efficient compared to more advanced algorithms like quicksort or mergesort, as it has an average and worst-case time complexity of 
𝑂
(
𝑛
2
)
O(n 
2
 ) where 
𝑛
n is the number of elements in the array. This is because it requires 
𝑛
n swaps in the worst case, even if the array is already sorted.

7. **Implementation Example**: Here's a simple implementation of selection sort in Java Script:

```js
const arr = [2,5,7,3,6,9,1]

const sorrtedArr = (arr)=>{
    for(let i = 0; i< arr.length-1; i++){
        // Assume the current index is the minimum
        let minIndex = i
        // Find the minimum element in the remaining unsorted array
        for(let j = i+1; j< arr.length; j++){
            if(arr[j] < arr[minIndex]){
                minIndex = j
            }
        }
        // Swap the found minimum element with the first element of the unsorted part
        [arr[i], arr[minIndex]]=[arr[minIndex], arr[i]]
    }
    return arr
}
console.log(sorrtedArr(arr))

```
