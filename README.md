# Course Scheduling Order

### Overview
This project provides a solution to the course scheduling problem, where a set of courses and prerequisites are given, and the task is to determine a valid order in which the courses should be taken. This project is implemented in Python, leveraging topological sorting (using Kahn's Algorithm) to handle dependency management for course prerequisites.

### Features
- Calculates a valid order for taking courses based on prerequisites.
- Detects cycles in course dependencies and returns an empty array if it’s impossible to complete all courses.
- Efficiently handles a large number of courses (up to 2000) and prerequisites.

### Implementation Details
This solution uses Kahn's Algorithm with a BFS approach:
1. **Graph Representation**: The courses and prerequisites are represented as a Directed Acyclic Graph (DAG).
2. **Topological Sort**: The algorithm uses an adjacency list and in-degrees array to calculate the order of courses.
3. **Edge Case Handling**: If the course dependencies contain cycles, the algorithm returns an empty list, indicating that it's impossible to complete all courses.

### Example Usage
```python
from solution import Solution

num_courses = 4
prerequisites = [[1, 0], [2, 0], [3, 1], [3, 2]]
solution = Solution()
order = solution.findOrder(num_courses, prerequisites)
print(order)  # Output: [0, 1, 2, 3] or [0, 2, 1, 3]
```

### Input/Output
- **Input**: `numCourses` (int) – total number of courses, `prerequisites` (list of lists) – prerequisites pairs.
- **Output**: A list representing the order in which to take the courses, or an empty list if not feasible.

### File Structure
- **solution.py**: Contains the `Solution` class and the `findOrder` method.
