
# Merge Sort implementation in JavaScript

## Runtime: O(nlogn)
## Best for: Online sorting

## Given an array of values, return the array sorted:
* Test case: arr: [1, 2, 4, 5, 8] ==> returns [1, 2, 4, 5, 8]
* Test case: arr: [1, 8, 5, 2, 4] ==> returns [1, 2, 4, 5, 8]

### Steps:
```pseudo
  1. Split array in half into left and right
  2. Split half arrays in half again and repeat until all values are split into their own arrays of length 1
  3. Take the first two arrays, and merge them to create a sorted array of length 2
  4. Take the next two arrays of length one and merge them to create another sorted array of length 2, and repeat until all remaining arrays are merged
  5. Next, take the first two arrays of length two and merge them into a sorted array of length 4
  6. For merging: check if arr1[0] < arr2[0], if so, put arr1[0] at the first spot in the new array. If not, put arr2[0] at the first spot.
  7.              Compare the next values until the array is filled.
  8. Repeat for all remaining arrays until a sorted array of length equal to the original array is created
```
### JavaScript Implementation:
```JS
mergeArrays = (arr1, arr2) => {
  let i = 0;
  let j = 0;
  let returnArr = [];
  while (i < arr1.length && j < arr2.length) {
    if (arr1[i] < arr2[j]) {
      returnArr.push(arr1[i]);
      i++;
    } else {
      returnArr.push(arr2[j]);
      j++;
    }
   }
   while (i < arr1.length) {
    returnArr.push(arr[i]);
    i++;
   }
   while (j < arr2.length) {
    returnArr.push(arr[j]);
    j++;
   }
   return returnArr;
  }
}
```

### Visualization
https://visualgo.net/en/sorting
Click on 'Insertion Sort'
    
  
