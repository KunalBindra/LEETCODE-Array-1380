# LEETCODE-Array-1380
Absolutely, let's dry run the provided `Solution` class to understand how it finds lucky numbers in a matrix:

**Lucky Number Definition:**

A lucky number in this context is the minimum element in a row that's also the maximum element in its corresponding column across the entire matrix.

**Dry Run:**

**Sample Matrix:**

```
matrix = [
  [3, 7, 2, 1],  // Row 1
  [4, 0, 5, 6],  // Row 2
  [8, 3, 1, 2]   // Row 3
]
```

**Explanation:**

1. **Outer Loop (find min in each row):**
   - **Iteration 1:**
      - `row` = `[3, 7, 2, 1]`
      - `getMinIndex(row)` is called. (See Step 2)
      - `minIndex` becomes 3 (index of minimum element 1 in row 1).
      - `row[minIndex]` (1) is compared with `maxNumOfColumn(matrix, minIndex)`. (See Step 3)
   - Since 1 is not the maximum element in the first column (4 is larger in row 2), the loop continues.

2. **getMinIndex Function:**
   - Iterates through each element (`row[j]`) in the current row.
   - If a smaller element is found, updates `minIndex` to its index.
   - In this case, `minIndex` remains 3 (smallest element is 1).

3. **maxNumOfColumn Function:**
   - Iterates through each row (`matrix[i]`) of the matrix.
   - Compares the element at the specified column (`j`) with the current maximum (`res`).
   - Updates `res` if a larger element is found.
   - Since 4 in row 2 is larger than 1 in all other rows (column 3), `res` remains 4.

4. **Outer Loop Continues:**
   - Similar process repeats for the remaining rows (2 and 3).
   - No row's minimum element is also the maximum in its corresponding column.

5. **Return:**
   - Since no lucky number is found, the outer loop finishes.
   - The function returns an empty `ArrayList<>`.

**Output:**

The dry run shows that for the given matrix, there are no lucky numbers. All rows have a minimum element that's not the maximum in its corresponding column.
