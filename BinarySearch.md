# Binary Search implementation in JavaScript

## Given a sorted array of values [], find if the value n is in the array:
* Test case: arr: [1, 2, 4, 5, 8, 9, 10, 12], num: 4 ==> returns 2
* Test case: arr: [1, 2, 4, 5, 8, 9, 10, 12], num: 7 ==> returns -1

```JS
binarySearch = (arr, num) => {
  let start = 0;
  let end = arr.length-1;
  let middle = Math.floor((start + end)/2);
  
  while (start < end) {
    if (num === arr[middle]) {
      // if number is found, return the index
      return middle;
    } else if (num < middle) {
      // number is below the middle, set the end pointer to the middle
      end = middle;
    } else {
      // number is above the middle, set the start pointer to the middle
      start = middle;
    }
    // re-calculate the middle pointer
    middle = Math.floor((start+end)/2);
  }
  return -1;
}
```
    
  
