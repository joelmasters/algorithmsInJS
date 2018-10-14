# Binary Search implementation in JavaScript

## Runtime: O(logn)

## Given a sorted array of values [], find if the value n is in the array:
* Test case: arr: [1, 2, 4, 5, 8, 9, 10, 12], num: 4 ==> returns 2
* Test case: arr: [1, 2, 4, 5, 8, 9, 10, 12], num: 7 ==> returns -1

### Steps:
```pseudo
  1. start a pointer at the first index of the array
  2. start a pointer at the last index of the array
  3. check the value at the middle index of the array
    4. if the value at the middle index does not equal the value we are looking for, continue
    5. if the value is less than the value at the middle index, move the last index to the middle index -1
    6. if the value is greater than the value at the middle index, move the start index to the middle index + 1
    7. calculate the index between the new start and end indices, and search again
  8. if the start index has crossed over the end index (start > end), the value we are looking for is not in the array
    9. return -1
```
### JavaScript Implementation:
```JS
binarySearch = (arr, num) => {
  let start = 0;
  let end = arr.length-1;
  let middle = Math.floor((start + end)/2);
  
  while (start <= end) {
    if (num === arr[middle]) {
      return middle;
    } else if (num < arr[middle]) {
      // number is below the middle, set the end pointer to the middle - 1
      //    - 1 because we know middle is not a solution, and don't need to check it again
      end = middle - 1;
    } else {
      // number is above the middle, set the start pointer to the middle + 1
      //    + 1 because we know middle is not a solution, and don't need to check it again
      start = middle + 1;
    }
    // re-calculate the middle pointer
    middle = Math.floor((start+end)/2);
  }
  return -1;
}
```
    
  
