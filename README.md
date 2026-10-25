# N-Puzzle Solver – A* Search

Lab 3 of the **Computational Intelligence** course (2024, Politecnico di Torino, Prof. Giovanni Squillero).

## The problem
The [n-puzzle](https://en.wikipedia.org/wiki/15_puzzle) (8-puzzle, 15-puzzle, …): a grid of numbered tiles with one empty space. Slide tiles into the empty space until they are in order. The goal is to reach the solved state in as few moves as possible.

## My approach
**A\* search** with the **Manhattan distance** heuristic:
- Each state is the grid; each action slides a tile into the empty space (up/down/left/right).
- **g(n):** number of moves made so far.
- **h(n):** sum of how far each tile is from its goal position (Manhattan distance). This never overestimates, so A* finds an optimal solution.
- A priority queue (heap) always expands the state with the lowest g + h, and a visited set avoids exploring the same state twice.
- The starting puzzle is created by making 1,000 random moves from the solved state, so it is always solvable.

## Example result (3×3)
```
Start:        Goal:
 7  2  0       1  2  3
 8  6  3       4  5  6
 4  1  5       7  8  0
```
Solved in **22 moves** (optimal), after evaluating 895 states.

The puzzle size is set by `PUZZLE_DIM` in the notebook.

## How to run
Open `n_puzzle.ipynb` in Jupyter or Google Colab.
Requirements: `tqdm`.
