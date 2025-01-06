# Lua Nested Table Iteration Bug

This repository demonstrates a potential issue with Lua's `pairs` iterator when used with nested tables and modifications to the table during iteration.

The `bug.lua` file contains a function that recursively iterates through a nested table. However, if the table were modified during iteration (e.g., by adding or removing elements), the iterator's behavior becomes undefined and may skip elements.

The `bugSolution.lua` file offers a solution using a copy to avoid this issue.

## Reproducing the Bug

Run `bug.lua`.  The output will be consistent but might not be what is expected if changes are made within the `foo` function during its operation.

## Solution

The `bugSolution.lua` file presents a revised approach. It creates a copy of the table before iteration, ensuring that modifications made during iteration won't affect the iteration itself.
