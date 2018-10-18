
# Insertion Sort implementation in JavaScript

## Runtime: O(n^2)
## Best for: Minimizing number of swaps (writing to memory)

## Given an array of values, return the array sorted:
* Test case: arr: [1, 2, 4, 5, 8] ==> returns [1, 2, 4, 5, 8]
* Test case: arr: [1, 8, 5, 2, 4] ==> returns [1, 2, 4, 5, 8]

### Steps:
```pseudo
  1. Look at the second element in the array. Compare it to the first element. If it is smaller, move it left, if it is larger, keep it there.
  2. Move to the third element in the array. Compare it to the previous elements until a place for it is found.
  3. Continue for all remaining elements in the array.
```
### JavaScript Implementation:
```JS
insertionSort = (arr) => {
  for (let i = 1; i < arr.length; i++) {
    let currentVal = arr[i];
    for (let j = i-1; j >= 0; j--) {
      if (currentVal < arr[j]) {
        arr[j+1] = arr[j];
      } else {
        arr[j+1] = currentVal;
        break;
      }
    }
  }
  return arr;
}
```

### Visualization
https://visualgo.net/en/sorting
Click on 'Insertion Sort'
    
  
