# Js-sorting-algorithm-diagram
排序算法图解、Javascript实现的排序算法图解

- 冒泡排序：[冒泡排序](http://htmlpreview.github.io/bubble-sort.html)
```
function bubbleSort(arr){
  for (let i = 0; i < arr.length; i++) {
      for (let j = 0; j < arr.length - i - 1; j++) {
          if (arr[j] > arr[j+1]) {
              let max = arr[j]
              arr[j] = arr[j+1]
              arr[j+1] = max
          }
      }
  }
  return arr
}
```
- 选择排序：[选择排序](http://htmlpreview.github.io/select-sort.html)
```
function selectSort(arr){
  for (let i=0; i<arr.length; i++){
      let min
      for (let j=i+1; j<arr.length; j++) {
          if(arr[j] < arr[i]) {
              min = arr[j]
              arr[j] = arr[i]
              arr[i] = min
          }
      }
  }
  return arr
}
```
- 插入排序：[插入排序](http://htmlpreview.github.io/insert-sort.html)
```
function insertionSort(arr) {
  var len = arr.length;
  var preIndex, current;
  for (var i = 1; i < len; i++) {
      preIndex = i - 1;
      current = arr[i];
      while (preIndex >= 0 && arr[preIndex] > current) {
          arr[preIndex + 1] = arr[preIndex];
          preIndex--;
      }
      arr[preIndex + 1] = current;
  }
  return arr;
}
```