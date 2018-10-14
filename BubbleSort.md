
# Bubble Sort implementation in JavaScript

## Runtime: O(n^2)

## Given a sorted array of values [], find if the value n is in the array:
* Test case: arr: [1, 2, 4, 5, 8, 9, 10, 12], num: 4 ==> returns 2
* Test case: arr: [1, 2, 4, 5, 8, 9, 10, 12], num: 7 ==> returns -1

### Steps:
```pseudo
  1. Compare first two elements in array
    2. If the first element is less than the second element, move to next element
    3. If the the first element is greater than the second element, switch the first and second elements
  4. Repeat next two elements in the array (2nd and 3rd)
  5. Repeat for all unsorted elements in the array
  6. When the end is reached, start over from the beginning
  7. Repeat until no changes are made
```
### JavaScript Implementation:
```JS
bubbleSort = (arr) => {
  let sortedCount = 0;
  while (sortedCount < arr.length) {
    let swapped = false;
    for (let i = 0; i < arr.length - 1 - sortedCount; i++) {
      if (arr[i] > arr[i+1]) {
        let temp = arr[i];
        arr[i] = arr[i+1];
        arr[i+1] = temp;
        swapped = true;
      }
    }
    if (!swapped) return arr;
    sortedCount++;
   }
}
```

### Visualization
https://visualgo.net/en/sorting

    
  
