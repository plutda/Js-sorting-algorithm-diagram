# Js-sorting-algorithm-diagram
排序算法图解、Javascript实现的排序算法图解

- 冒泡排序：[冒泡排序图解](https://plutda.github.io/Js-sorting-algorithm-diagram/bubble-sort.html)
- 冒泡排序是一种简单直观的排序算法，其基本思想是不断比较相邻的两个元素并交换顺序，使较大（或较小）的元素逐渐“浮”到数组的末端。
  其过程可以简单描述为以下几个步骤：
  从数组中第一个元素开始，把当前元素和下一个元素进行比较。如果当前元素比下一个元素大（或小），则交换它们的位置；
  移动到下一个位置后，再次比较当前元素和其下一个元素，重复上述操作，直到没有可以交换的元素；
  对于数组中的所有元素，重复以上步骤，直到排序完成。
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
- 选择排序：[选择排序图解](https://plutda.github.io/Js-sorting-algorithm-diagram/select-sort.html)
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
- 插入排序：[插入排序图解](https://plutda.github.io/Js-sorting-algorithm-diagram/insert-sort.html)
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

- 快速排序：[冒泡排序图解](https://plutda.github.io/Js-sorting-algorithm-diagram/quick-sort.html)
- 快速排序是一种基于分治思想的、广泛应用的排序算法，其基本思想是通过一趟排序将待排序记录分隔成独立的两部分，其中一部分记录的关键字均比另一部分记录的关键字小，然后分别对这两部分记录继续进行排序，以  达到整个序列有序的效果。快速排序的过程可以简单描述为以下几个步骤：

  从待排序数列中选择一个元素作为基准（通常是第一个元素或最后一个元素）；
  将待排序数列划分成两个子序列，其中一部分的元素都要比基准元素小，另一部分的元素则都要比基准元素大；
  对两个子序列重复执行步骤 1 和 2，直到所有子序列都只包含一个元素。
```
function quickSort(arr) {
  if (arr.length <= 1) {
    return arr; // 如果数组只有一个元素或为空，直接返回原数组
  }

  const pivot = arr[0]; // 选择第一个元素作为基准
  const left = [];
  const right = [];

  for (let i = 1; i < arr.length; i++) { // 从第二个元素开始遍历
    if (arr[i] < pivot) {
      left.push(arr[i]); // 将比基准小的元素放到左边数组
    } else {
      right.push(arr[i]); // 将比基准大的元素放到右边数组
    }
  }

  return quickSort(left).concat(pivot, quickSort(right)); // 递归调用自身，将左右数组与基准合并
}
```
