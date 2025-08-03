QuadTree Grid Compression
This project implements a QuadTree compression algorithm for binary grids (2D arrays of 0's and 1's). The algorithm recursively partitions the grid into quadrants, compressing regions of uniform values into leaf nodes and subdividing mixed regions into internal nodes with four children.
Unlike approaches that copy subgrids during recursion, this solution optimizes performance by passing coordinate indices (x, y, size) to represent subregions, which eliminates unnecessary slicing and memory overhead.

📂 Project Structure
.
├── quad_tree.py     # Main QuadTree compression algorithm
├── README.md        # Project documentation
└── example.py       # Example usage and test grids
🚀 Features
Recursive QuadTree construction from binary grids.
Efficient subgrid processing via index-based traversal (no slicing).
Leaf node compression for homogeneous regions.
Handles grids of size N x N (where N is a power of 2).
📝 Problem Description
Given an N x N grid of binary values (0 or 1), represent it using a QuadTree where:
Leaf nodes represent uniform regions (all 0's or all 1's).
Internal nodes subdivide into top-left, top-right, bottom-left, and bottom-right children.
🧑‍💻 How It Works
Start with the entire grid region.
Count the number of 1's in the current region.
If the region is homogeneous (all 0's or all 1's), create a leaf node.
Otherwise, subdivide the region into four quadrants and recursively build child nodes.
Continue until all leaf nodes represent uniform areas.
The algorithm avoids grid slicing by passing only the top-left coordinates and the size of the current subgrid, thus preserving O(1) space for each recursive call.
🖥️ Example Usage
from quad_tree import Solution

grid = [
    [1, 1, 0, 0],
    [1, 1, 0, 0],
    [0, 0, 1, 1],
    [0, 0, 1, 1]
]

solution = Solution()
quad_tree_root = solution.construct(grid)
📊 Example Grid
Input Grid:
1 1 0 0
1 1 0 0
0 0 1 1
0 0 1 1

QuadTree Representation:
- Root (Internal Node)
  ├── Top Left: Leaf (val=1)
  ├── Top Right: Leaf (val=0)
  ├── Bottom Left: Leaf (val=0)
  └── Bottom Right: Leaf (val=1)
🧠 Applications
Image compression
Spatial indexing (e.g., GIS)
2D hierarchical data partitioning
Efficient region queries in graphics and simulations
📜 License
This project is open-source and available under the MIT License.
