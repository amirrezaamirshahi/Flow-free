# Dot Graph Solver: Color Path Connection Puzzle

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/downloads/)
[![PyGame](https://img.shields.io/badge/PyGame-2.0.0+-orange.svg)](https://www.pygame.org/)

This project implements a **Dot Graph Solver** for a color path connection puzzle, inspired by games like *Flow Free*. The objective is to connect pairs of colored dots on a grid using paths of the same color that fill the entire grid without overlapping. The solver employs a backtracking algorithm with Manhattan distance heuristics for efficient pathfinding and includes a Pygame-based GUI for visual representation.

The system handles puzzles of various grid sizes (e.g., 6x6) with multiple colored dot pairs, outputting the solution process in the console and displaying the final configuration graphically. It's suitable for puzzle enthusiasts, algorithm researchers, or developers interested in constraint satisfaction and pathfinding problems.

## 🎯 Project Overview

This project solves a grid-based puzzle where:
- Grid cells can be empty, colored dots, or parts of colored paths.
- Each pair of same-colored dots must be connected via a continuous path of that color.
- Paths must not overlap, and the grid must be fully filled for a valid solution.
- The backtracking solver prioritizes moves based on Manhattan distance and recent actions to optimize exploration.
- A Pygame GUI renders the grid with distinct colors for paths and dots.

Key highlights:
- Heuristic-driven backtracking for quick solutions.
- Connectivity validation using DFS (Depth-First Search).
- Support for customizable puzzles via input dictionaries.
- Console output for solving time and grid states, plus interactive visualization.

Tested on 6x6 grids with 5-7 color pairs, solving in under 1 second for most cases.

## 🚀 Features

- **Grid Management**: NxN matrix representation using NumPy for efficient operations.
- **Solver Engine**: Backtracking with priority queue for nearest empty cells, ensuring valid paths.
- **Validation Rules**: Checks for path connectivity, no overlaps, and grid completeness.
- **Visualization**: Pygame GUI displaying grids with colored rectangles (paths) and circles (dots).
- **Customization**: Easy modification of grid size and dot positions via input data.

| Feature | Description | Supported |
|---------|-------------|-----------|
| Grid Size | Configurable NxN (e.g., 6x6) | ✅ |
| Algorithm | Backtracking + Manhattan Heuristic | ✅ |
| Path Checks | DFS-based connectivity & non-overlap | ✅ |
| GUI | Real-time Pygame rendering | ✅ |
| Outputs | Console prints & graphical display | ✅ |

## 📋 Prerequisites

- Python 3.8 or higher
- NumPy for array operations
- PyGame for GUI visualization
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

4. Run the solver (no additional setup needed; input data is defined in the script).

## 🗂️ Project Structure

```
dot-graph-solver/
├── solver.py              # Main script with Dot and DotGraph classes
├── requirements.txt       # Dependencies
├── README.md              # This file!
└── LICENSE                # MIT License
```

## 🔧 Usage

### 1. Run the Solver
Execute the script to solve a predefined puzzle and launch the GUI:
```bash
python solver.py
```

### 2. Customize Puzzles
Edit the `input_data` dictionary in `solver.py` to define new puzzles:
```python
input_data = {
    "green": [(0, 5), (4, 3)],
    "magenta": [(2, 1), (3, 5)],
    "red": [(4, 1), (3, 3)],
    "blue": [(5, 3), (4, 5)],
    "light_yellow": [(2, 2), (4, 4)],
}

# Create and solve
dot_graph = DotGraph(6, input_data)  # Grid size 6x6
dot_graph.show_solve_show()  # Console output with timing
dot_graph.display()          # Launch Pygame GUI
```

- **Grid Size**: Set via the first argument to `DotGraph` (must match coordinates).
- **Colors**: Use predefined colors like "red", "green", etc.; extend the colors dict in `display()` for more.

### 3. Outputs
- **Console**: Shows initial/final grid states with Unicode icons (● for dots, ■ for paths) and solving time.
  Example:
  ```
  6x6, 5 colors
  [[□ □ □ □ □ ●] ...]
  0.234 seconds
  [[■ ■ ■ ■ ■ ●] ...]
  ```
- **GUI**: Interactive window displaying the solved grid. Close the window to exit.

## 📈 Results & Performance

- **Solving Speed**: ~0.2-1.0 seconds for 6x6 grids with 5 colors.
- **Scalability**: Works for small-to-medium grids; larger ones may need optimization.
- **Accuracy**: Full validation ensures all paths connect without violations.

Challenges:
- Exponential complexity in backtracking for very large or constrained puzzles.
- GUI is display-only; future enhancements could add interactivity.

## 🤝 Contributing

Contributions are welcome! Fork the repo, create a feature branch, and submit a PR. Suggested improvements:
- Add puzzle generation for random challenges.
- Implement faster heuristics (e.g., A* search).
- Support saving solved puzzles to files.
- Enhance GUI with animation of the solving process.

## 📞 Authors & Acknowledgments

- **Primary Developer**: [Your Name] – [your.email@example.com](mailto:your.email@example.com)
- Inspired by path-connection puzzles like Flow Free.
- Thanks to NumPy, PyGame, and Termcolor for core functionality.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🔗 Links

- [Demo Video](https://youtu.be/example) (TBD)
- Questions? Open an [Issue](https://github.com/yourusername/dot-graph-solver/issues)!

---

*Last Updated: September 18, 2025*  
*Stars: ⭐ Help us reach 100!*# Dot Graph Solver: Color Path Connection Puzzle

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
