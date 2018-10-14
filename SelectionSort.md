
# Selection Sort implementation in JavaScript

## Runtime: O(n^2)
## Best for: Minimizing number of swaps (writing to memory)

## Given an array of values, return the array sorted:
* Test case: arr: [1, 2, 4, 5, 8] ==> returns [1, 2, 4, 5, 8]
* Test case: arr: [1, 8, 5, 2, 4] ==> returns [1, 2, 4, 5, 8]

### Steps:
```pseudo
  1. Look at all the elements in the array and find the minimum
  2. Swap the value in the first position in the array with the value of the minimum
  3. Look at all elements in the array except the first and find the minimum
  4. Swap the value in the second position in the array with the value of that minimum
  5. Repeat for all spaces in the array
```
### JavaScript Implementation:
```JS
selectionSort = (arr) => {
  for (let i = 0; i < arr.length; i++) {
    let minIndex = i;
    for (let j = i + 1; j < arr.length; j++) {
      if (arr[j] < arr[minIndex]) {
        minIndex = j;
      }
    }
    if (i !== minIndex) {
      [arr[i], arr[minIndex]] = [arr[minIndex], arr[i]];
    }
  }
  return arr;
}
```

### Visualization
https://visualgo.net/en/sorting
Click on 'Bubble Sort'
    
  
