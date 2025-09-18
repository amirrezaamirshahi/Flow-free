


[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/downloads/)
[![PyGame](https://img.shields.io/badge/PyGame-2.0.0+-orange.svg)](https://www.pygame.org/)

This project implements a **Dot Graph Solver** for a color path connection puzzle, similar to the game Flow Free. The goal is to connect pairs of colored dots on a grid using paths of the same color, ensuring that paths do not overlap and the entire grid is filled. The solver uses a backtracking algorithm with Manhattan distance as a heuristic and provides a Pygame-based GUI for visualization.

The system efficiently solves puzzles with various grid sizes (e.g., 6x6) and multiple pairs of colored dots, displaying the solution process and final configuration. It's ideal for puzzle enthusiasts, algorithm researchers, or game developers exploring pathfinding and constraint satisfaction problems.

## 🎯 Project Overview

This project provides a solver for a grid-based puzzle where:
- Each grid cell can be empty, a colored dot, or part of a colored path.
- Pairs of colored dots (e.g., red, green) must be connected by continuous paths of the same color.
- Paths cannot overlap, and the entire grid must be filled for a valid solution.
- The solver uses a backtracking approach, prioritizing moves based on Manhattan distance and recent actions.
- A Pygame GUI visualizes the grid, dots, and paths with distinct colors.

Key features:
- Efficient pathfinding with Manhattan distance heuristics.
- Backtracking to explore valid configurations.
- Pygame-based interactive visualization.
- Support for customizable grid sizes and color pairs.
- Validation of solvable puzzles using connectivity checks.

The project was tested on 6x6 grids with up to 7 colored dot pairs, achieving fast solutions (<1 second for typical cases).

## 🚀 Features

- **Grid Representation**: NxN grid with colored dots and paths.
- **Solver Algorithm**: Backtracking with Manhattan distance and recent-action prioritization.
- **Path Validation**: Ensures non-overlapping paths and grid connectivity.
- **Visualization**: Pygame GUI showing dots (●) and paths (■) in vibrant colors.
- **Custom Inputs**: Supports user-defined grid sizes and dot pair configurations.

| Feature | Description | Supported |
|---------|-------------|-----------|
| Grid Size | Configurable NxN grids (e.g., 6x6) | ✅ |
| Solver | Backtracking with Manhattan distance | ✅ |
| Validation | Path connectivity and non-overlap checks | ✅ |
| GUI | Pygame-based grid visualization | ✅ |
| Outputs | Console output and graphical display | ✅ |

## 📋 Prerequisites

- Python 3.8 or higher
- PyGame for visualization
- NumPy for efficient grid operations
- Termcolor for colored console output

### Installation

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/dot-graph-solver.git
   cd dot-graph-solver
   ```

2. Create a virtual environment:
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

   **requirements.txt** contents:
   ```
   numpy>=1.21.0
   pygame>=2.0.0
   termcolor>=1.1.0
   ```

4. Prepare input data:
   - Define dot pairs in a dictionary (e.g., `input_data` in the script).
   - Example format:
     ```python
     input_data = {
         "green": [(0, 5), (4, 3)],
         "magenta": [(2, 1), (3, 5)],
         "red": [(4, 1), (3, 3)],
         "blue": [(5, 3), (4, 5)],
         "light_yellow": [(2, 2), (4, 4)],
     }
     ```

## 🗂️ Project Structure

```
dot-graph-solver/
├── src/
│   └── solver.py         # Main DotGraph solver and Dot class
├── input_data.py        # Sample input configurations
├── requirements.txt     # Dependencies
├── README.md            # This file!
└── LICENSE              # MIT License
```

## 🔧 Usage

### 1. Run the Solver
Execute the main script to solve and visualize the puzzle:
```bash
python src/solver.py
```

### 2. Define Custom Input
Modify `input_data` in the script to create new puzzles:
```python
# In solver.py
input_data = {
    "green": [(0, 5), (4, 3)],
    "magenta": [(2, 1), (3, 5)],
    "red": [(4, 1), (3, 3)],
    "blue": [(5, 3), (4, 5)],
    "light_yellow": [(2, 2), (4, 4)],
}
dot_graph = DotGraph(6, input_data)
dot_graph.show_solve_show()  # Print solution process
dot_graph.display()          # Show GUI
```

### 3. Visualize Output
- **Console Output**: Displays the initial grid, solving time, and final grid with colored paths (using termcolor).
- **GUI Output**: Pygame window showing the grid with colored rectangles (paths) and black circles (dots).

Sample Console Output:
```
6x6, 5 colors
[[□ □ □ □ □ ●] ...]
0.234 seconds
[[■ ■ ■ ■ ■ ●] ...]
```

Sample GUI: [Insert screenshot link, e.g., `screenshots/solution.png`]

## 📈 Results

- **Performance**: Solves 6x6 grids with 5-7 color pairs in ~0.2-1.0 seconds.
- **Correctness**: Validates solutions with connectivity checks and non-overlap constraints.
- **Visualization**: Clear distinction between dots and paths in the GUI, with customizable colors.

Challenges:
- Larger grids (>10x10) may increase solving time due to backtracking.
- Complex puzzles with tight constraints may require heuristic tuning.

## 🤝 Contributing

Contributions welcome! Fork the repo, create a feature branch, and submit a PR. Focus areas:
- Optimize backtracking algorithm for larger grids.
- Add support for saving/loading puzzle configurations.
- Enhance GUI with interactive path drawing.

## 📞 Authors & Acknowledgments

- **Primary Developer**: [Amirreza Amirshahi] – [amirreza2002amirshahi@gmail.com](mailto:amirreza2002amirshahi@gmail.com)
- Thanks to PyGame and NumPy teams for robust libraries.
- Inspired by *Flow Free* and similar path-connection puzzles.




---

*Last Updated: September 18, 2025*  
*Stars: ⭐ Help us reach 100!*
