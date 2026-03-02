# Dynamic Pathfinding Agent 

## Project Overview

This project implements a Dynamic Pathfinding Agent designed to navigate a grid-based environment using informed search algorithms. The agent computes a path from a fixed Start node to a fixed Goal node while adapting to dynamically appearing obstacles during execution.

The system includes a graphical user interface (GUI) built with Tkinter that visualizes search progress and displays performance metrics in real time.

---

## Objectives

* Implement A* Search and Greedy Best-First Search (GBFS)
* Support two heuristic functions: Manhattan and Euclidean
* Enable dynamic obstacle spawning during agent movement
* Perform automatic re-planning when the current path becomes blocked
* Provide an interactive grid editor
* Display real-time performance metrics

---

## Environment Specifications

The environment satisfies the following requirements:

* Grid-based world (default: 20 × 20)
* Fixed Start node (top-left) and Goal node (bottom-right)
* User-defined obstacle density for random map generation
* Interactive wall placement and removal via mouse clicks
* No use of static text-based map files
* Continuous visualization of search progress

---

## Implemented Algorithms

### A* Search

Evaluation function:

f(n) = g(n) + h(n)

Where:

* g(n) is the path cost from the start to node n
* h(n) is the heuristic estimate to the goal

Characteristics:

* Complete and optimal with admissible heuristics
* Explores more nodes than Greedy in many cases
* Produces the shortest path

---

### Greedy Best-First Search (GBFS)

Evaluation function:

f(n) = h(n)

Characteristics:

* Uses only heuristic guidance
* Typically faster than A*
* Does not guarantee optimal paths
* May get trapped in local minima

---

## Heuristic Functions

### Manhattan Distance

|x₁ − x₂| + |y₁ − y₂|

Appropriate for four-directional grid movement without diagonals.

### Euclidean Distance

√((x₁ − x₂)² + (y₁ − y₂)²)

Provides straight-line distance estimation between nodes.

---

## Dynamic Obstacle Handling

When Dynamic Mode is enabled:

* New obstacles spawn randomly during agent movement
* The agent continuously monitors the next step
* If the planned path becomes blocked:

  * The agent immediately recomputes a path from its current position
* This simulates real-world navigation in changing environments

---

## Visualization Scheme

| Element                  | Color      |
| ------------------------ | ---------- |
| Agent (current position) | Blue       |
| Goal                     | Red        |
| Frontier nodes           | Yellow     |
| Visited nodes            | Light Blue |
| Final path               | Green      |
| Obstacles                | Black      |

---

## Performance Metrics

The GUI displays the following metrics:

* Nodes Visited: total number of expanded nodes
* Path Cost: length of the computed path
* Execution Time: time required to compute the solution (milliseconds)

These metrics update after each search execution.

---

## How to Run

### Requirements

* Python 3.x
* Tkinter (usually included with Python)

### Execution

Run the program using:

```bash
python main.py
```

---

## Usage Instructions

1. Select the search algorithm:

   * A*
   * Greedy

2. Select the heuristic:

   * Manhattan
   * Euclidean

3. Enter obstacle density (recommended: 0.15–0.25)

4. Click **Random Map**

5. Click **Run**

6. Optionally enable **Dynamic Mode** to observe real-time replanning.

---

## Recommended Test Configurations

The following combinations should be demonstrated:

* A* with Manhattan heuristic
* A* with Euclidean heuristic
* Greedy with Manhattan heuristic
* Greedy with Euclidean heuristic
* Dynamic Mode enabled scenario

---

## Expected Behavior

* The agent finds a path when one exists
* Metrics update correctly after each run
* The agent replans automatically when obstacles appear on its path
* Visualization reflects frontier, visited nodes, and final path accurately

---

## Limitations

* Very high obstacle density (> 0.35) may produce unsolvable maps
* Greedy Best-First Search does not guarantee optimal solutions
* Performance may vary depending on obstacle distribution

---

## Author

Hafsa
National University of Computer & Emerging Sciences
Chiniot–Faisalabad Campus

---

## Status

All required features for Question 06 have been implemented and verified.
