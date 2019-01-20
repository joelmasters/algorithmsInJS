
# Quick Sort implementation in JavaScript

## Runtime: O(nlogn)
## Best for: Online sorting

## Given an array of values, return the array sorted:
* Test case: arr: [1, 2, 4, 5, 8] ==> returns [1, 2, 4, 5, 8]
* Test case: arr: [1, 8, 5, 2, 4] ==> returns [1, 2, 4, 5, 8]

### Steps:
```pseudo
  1. Select a pivot point (can be any element in the array)
  2. Move all of the elements that are less than the pivot value to the left of it, and all the elements that are greater to the right. The pivot is now in the correct location in the array.
  3. Starting from the left, take the first element and move all elements that are less to the left, and all values greater to the right. (We only need to look at elements up to the pivot-1).
  4. Repeat until the left is sorted.
  5. Repeat the same steps for the right side.
```
### JavaScript Implementation:
```JS
pivot = (arr, start=0, end=arr.length+1) => {
  // arr: array to find pivot position of 
  let swapIndex = start; // number of elements less than pivot
  let pivot = arr[start]; // pivot value
  for (let i = start+1; i < arr.length; i++) {
    if (arr[i] < pivot) {
      swapIndex++;
      [arr[i], arr[swapIndex]] = [arr[swapIndex], arr[i]];
    }
  }
  [arr[start], arr[swapIndex]] = [arr[swapIndex], arr[start]];
  return swapIndex;
}

quickSort = (arr, left=0, right=arr.length-1) => {
  if (left < right) {
    let pivotIndex = pivot(arr, left, right);
    quickSort(arr, left, pivotIndex-1);
    quickSort(arr, pivotIndex+1, right);
  }
  return arr;
}
```

### Visualization
https://visualgo.net/en/sorting
Click on 'Quick Sort'
    
  
