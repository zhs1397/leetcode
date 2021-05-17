leetcode
====
records of the leetcode practice from May to August 2021 

## Table of Contents

- [May 17th](#may-17th)


## May 17th
### Rotate Matrix LCCI 
[link](https://leetcode-cn.com/problems/rotate-matrix-lcci/)<br>
① Use a horizontal flip followed by a diagonal flip <br>
```python
class Solution:
        n = len(matrix)
        for i in range(n//2):
            for j in range(n):
                matrix[i][j], matrix[n-i-1][j] = matrix[n-i-1][j], matrix[i][j]
        for i in range(n):
            for j in range(i):
                matrix[i][j], matrix[j][i] = matrix[j][i], matrix[i][j]
```
② Use a new matrix to store the matrix after rotation
```python
class Solution:
    def rotate(self, matrix: List[List[int]]) -> None:
        n = len(matrix)
        # Python 这里不能 matrix_new = matrix 或 matrix_new = matrix[:] 因为是引用拷贝
        matrix_new = [[0] * n for _ in range(n)]
        for i in range(n):
            for j in range(n):
                matrix_new[j][n - i - 1] = matrix[i][j]
        # 不能写成 matrix = matrix_new
        matrix[:] = matrix_new
```

        



