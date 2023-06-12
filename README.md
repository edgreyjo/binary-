# binary-
Binary search is an efficient algorithm for finding a specific element in a sorted array.
/**
 * Performs binary search on a sorted array to find the index of a target element.
 * @param {Array} array - The sorted array to search in.
 * @param {*} target - The element to search for.
 * @returns {number} - The index of the target element, or -1 if it is not found.
 */
function binarySearch(array, target) {
  let left = 0;
  let right = array.length - 1;

  while (left <= right) {
    let mid = Math.floor((left + right) / 2);
    if (array[mid] === target) {
      return mid;
    } else if (array[mid] < target) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }

  return -1;
}

// Example usage:
const sortedArray = [1, 3, 5, 7, 9, 11, 13];
const targetElement = 7;
const targetIndex = binarySearch(sortedArray, targetElement);

console.log(`The index of ${targetElement} is ${targetIndex}.`);
