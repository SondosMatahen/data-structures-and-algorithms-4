# Merge Sort  


## 401 challenges CC 28  
  Review the pseudocode, then trace the algorithm by stepping through the process with the provided sample array.  
  Document your explanation by creating a blog article that shows the step-by-step output after each iteration through some sort of visual.



## Approach & Efficiency
- Big O :
   - time : O(n)
   - space :O(1)


## Pseudocode
  ```
   ALGORITHM QuickSort(arr, left, right)
    if left < right
        // Partition the array by setting the position of the pivot value 
        DEFINE position <-- Partition(arr, left, right)
        // Sort the left
        QuickSort(arr, left, position - 1)
        // Sort the right
        QuickSort(arr, position + 1, right)

   ALGORITHM Partition(arr, left, right)
    // set a pivot value as a point of reference
    DEFINE pivot <-- arr[right]
    // create a variable to track the largest index of numbers lower than the defined pivot
    DEFINE low <-- left - 1
    for i <- left to right do
        if arr[i] <= pivot
            low++
            Swap(arr, i, low)

     // place the value of the pivot location in the middle.
     // all numbers smaller than the pivot are on the left, larger on the right. 
     Swap(arr, right, low + 1)
    // return the pivot index point
     return low + 1

   ALGORITHM Swap(arr, i, low)
    DEFINE temp;
    temp <-- arr[i]
    arr[i] <-- arr[low]
    arr[low] <-- temp
  ```

## JavaScript Code  

  ``` 
   function quickSort(arr, left, right){
  if (left<right){
    let position = partition(arr, left, right);

    quickSort(arr, left, position - 1);
  
    quickSort(arr, position + 1, right);
  }
  return arr;
}
  
function partition(arr, left, right){
  let pivot = arr[right];
  let low = left - 1;

  for(let i=left; i<right;i++ ){
    if( arr[i] <= pivot ){
      low++;
      swap(arr, i, low);
    }
  }
  swap(arr, right, low + 1);
  return low+1;
}

function swap(arr, i, low){
  let temp ;
  temp = arr[i];
  arr[i]=arr[low];
  arr[low]=temp;
}

  ```

## Solution
![quickSort](../../assets/quickSort.jpeg)

