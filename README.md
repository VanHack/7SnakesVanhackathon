# 7SnakesVanhackathon
A Vanhackathon's challenge by Ascent Software

### Problem:

Consider a grid N*N. A 7-Snake is a sequence of cells c1, c2, …,c7 in a grid such that each cell is adjacent to the one before it. More formally, for 1 ≤ i < 7, ci+1 is adjacent to ci. Two cells a and b are adjacent if b is to the top, bottom, left, or right of a. Given an arbitrary ordering of the cells in a 7-Snake, each cell ci, can only be adjacent to ci-1 or ci+1.  Note that this exclude cycles.
The problem is very simple to describe. Given a grid of integers, find a pair (two) of 7-Snakes A and B that has the property that the sum of the integers in 7-Snake A is exactly the same as the sum of integers in 7-Snake B. 

1. The two 7-Snakes must be distinct. They cannot share cells.
2. In general there may be more than one pair of 7-Snakes with the required property. Your program need only find one pair.
3. If no such pair exists the program should output ‘FAIL’. Otherwise it should output the first pair it finds that has the above property.
4. The solution depends on your ability to enumerate the set of all pairs of distinct 7-Snakes in the given grid.
5. In general, the input grid can be any (square) size. The grid should be stored in CSV format on disk and loaded by your solution. This will allow us to test your solution on various test examples. The integers in each cell must range from 1 to 256.

### Algorithm:

To solve the 7-Snake problem the program follow the following steps:

* Read the csv file and transform into an matrix
* Begin to explore the matrix from top left corner to bottom right corner.
* Enumerate each cell from 0 to N * N - 1.
* Find all possible snakes starting from cell 0 (considering all the restrictions).
* Keep all valid snakes started from 0 in an array in their respective position (index 0).
* Do this for all other cells, resulting in an array of arrays where in each index we have several snakes started in the cell represented by this index.
* Finally, compare all the snakes that do not belong to the same group, always ignoring snakes that overlap.
* If two snakes that meet the above conditions and whose sums are the same are found, the problem is solved.
* If there are no two snakes satisfying the above condition, then there is no valid pair.

I chose HTML / Javascript because I did not just want to solve the problem, but also create a presentable interface. In addition, I wanted to make it easier for the end user to upload the file. With the HTML input tag is very easy, just select the file in your folder.

### Future improvements:
* Optimize the code.
* Create a beautiful layout.
* Make the solution of the problem animated by drawing the position of the snakes in each iteration of the algorithm.

**Hope you enjoy it!**