# technical-writing

This repository contains several drafts of mine for practicing technical writing and documentation as a developer.
As well as markdown prsentation.

**declaration**\
This repository is more like personal note such as a blog post. There would be icluded a personal opinion from my side.


# bubble sort

```
The mechanism of n-i-1 in the range of the inner loop:
Array: [5, 2, 8, 12, 1, 6]
n = 6

i = 0 (first pass):
  j goes from 0 to n-i-1 = 6-0-1 = 5
  We compare: (0,1), (1,2), (2,3), (3,4), (4,5)
  After this pass: [2, 5, 8, 1, 6, 12]  (12 is in its final position)

i = 1 (second pass):
  j goes from 0 to n-i-1 = 6-1-1 = 4
  We compare: (0,1), (1,2), (2,3), (3,4)
  After this pass: [2, 5, 1, 6, 8, 12]  (8 and 12 are in their final positions)

i = 2 (third pass):
  j goes from 0 to n-i-1 = 6-2-1 = 3
  We compare: (0,1), (1,2), (2,3)
  And so on...
```

```python
def bubbleSort(arr):
    n = len(arr)

    for i in range(arr):
        flag = Flase

        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
                flag = Ture
        if not flag:
            break

    return arr
```


