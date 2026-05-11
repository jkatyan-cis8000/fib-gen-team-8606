# ARCHITECTURE.md

Written by team-lead before spawning teammates. This is the shared blueprint —
teammates read it to understand what they are building and how their module fits.
Update it when the structure changes; do not let it drift from the actual code.

## Module Structure

- `fib_generator.py`: Core Fibonacci generation logic with `generate_fibonacci(limit: int) -> list[int]`
- `cli.py`: Command-line interface that parses arguments and displays results
- `tests/test_fib.py`: Unit tests for the generator function
- `main.py`: Entry point that orchestrates CLI and generator

## Interfaces

- `fib_generator.py` exposes:
  - `generate_fibonacci(limit: int) -> list[int]`: Returns all Fibonacci numbers <= limit
  - `generate_count(count: int) -> list[int]`: Returns first `count` Fibonacci numbers
- `cli.py` depends on `fib_generator`; exposes `main()` function
- `tests/test_fib.py` imports from `fib_generator` for unit tests

## Shared Data Structures

- `list[int]`: List of Fibonacci numbers (ascending order)
- `limit: int`: Upper bound for Fibonacci values (inclusive)

## External Dependencies

- None required - uses pure Python
