# Percolation Simulation with Stack-Based DFS

This project simulates **percolation** on a 2D grid — a process where liquid flows through a porous material — using a Python implementation of **stack-based Depth-First Search (DFS)**.

## 🔄 Why Stack-based DFS?

Originally, we implemented DFS using recursion.
However, during large-scale simulations (e.g., 1000×1000 grids), the program ran into a **RecursionError** due to Python’s recursion depth limit.
To solve this issue, we rewrote the algorithm using an **explicit stack**, which made the program capable of handling larger grids more reliably.

---

## 🧩 Features

- Matrix generator with customizable open-cell probability
- Efficient stack-based DFS algorithm
- Top-to-bottom percolation path detection
- Optional graph-based analysis of percolation success rate
- Presentation slides included for explanation and demonstration

---

## 📦 Matrix Generator

```python
generate_matrix(n=100, prob=0.4)
```

Creates an (n+2) × (n+2) matrix padded with zeros to simplify boundary checking.
The probability `prob` controls how likely each inner cell is set to `1` (open).

---

## 🔍 Stack-based DFS (`stack_check()`)

Replaces recursive DFS with an iterative version using a stack.
This avoids Python’s recursion limits and improves performance on larger grids.

### Basic idea:

- Start from all open cells in the top row
- Use a stack to explore connected open cells
- If any path reaches the bottom row → **percolation occurs**

---

## ✅ Percolation Detection (`find_path()`)

After running DFS, this function checks whether any of the visited cells reached the bottom row.
If so, a percolating path exists from top to bottom.

---

## 📊 Visualization Notice

This repository includes graphs that show the relationship between open-cell probability and percolation likelihood.

> These visualizations were created as part of a group project and were not implemented by the primary author(s) of this repository.
> They are included for educational purposes only, and we refrain from identifying contributors for privacy reasons.

---

## 📄 Presentation

Please refer to the attached PDF:
**`Percolation_Detection_Finding_a_Path_from_Top_to_Bottom.pdf`**
This presentation explains the project background, methodology, and key findings.

---

## 💡 Possible Extensions

- 3D percolation using cube-shaped matrices
- Hexagonal grids with 6-directional neighbors
- GUI-based interactive simulations
- Animated visualization of the percolation process
- Dynamic programming to cache and reuse DFS paths

---

## 👥 Credits

- Core simulation and algorithm (e.g., `generate_matrix`, `stack_check`, `find_path`):
  The core simulation logic was primarily developed by the repository maintainer,
  with valuable input from a team member who helped improve parameter handling and simplify the code.

- Visualization components:
  Added as part of group collaboration (not authored by the maintainer).

---

## 🔒 License

This project is shared for **educational and academic use only**.
Please do **not reuse or redistribute** the contents, especially the visualization parts, without permission.
If you are interested in extending or adapting this work, feel free to contact the repository maintainer.
