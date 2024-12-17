# Silent Map Access in Go: A Subtle Bug

This repository demonstrates a common, yet easily missed, issue in Go: accessing elements in a map that do not exist.  Instead of raising an error, accessing a non-existent key returns the zero value for the map's value type. This silent failure can be a significant source of hard-to-find bugs.

## The Bug

The `bug.go` file contains a simple program that attempts to access a key in an uninitialized map.  Notice that it does not panic. Instead, it prints `0`, the zero value for the `int` type.

## The Solution

The `bugSolution.go` file demonstrates a better approach.  It first checks if the key exists before accessing it, preventing unexpected behavior.

## Lessons Learned

* Always check for the existence of a key before accessing it from a map.
* Be aware of Go's default behavior of returning zero values for non-existent map keys.
* Use explicit error handling to catch unexpected situations and make your code more robust.
