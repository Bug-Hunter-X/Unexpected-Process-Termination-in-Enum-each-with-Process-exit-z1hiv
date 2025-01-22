# Elixir Bug: Unexpected Process Termination

This repository demonstrates a subtle bug in Elixir code involving the use of `Enum.each` and `Process.exit` within the function. The issue arises when `Process.exit` is called prematurely, preventing the `Enum.each` from iterating through all elements.

The `bug.ex` file contains the erroneous code. The `bugSolution.ex` file presents a corrected version that addresses the premature termination issue.

## Bug Description
The provided code snippet uses `Enum.each` to iterate over a list of integers. However, when a specific condition is met (x equals 3), `Process.exit(self(), :normal)` is called, which immediately terminates the current process before the loop completes.  This unexpected behavior prevents the program from printing all the remaining elements.

## Solution
The solution demonstrates how to gracefully handle the logic without abruptly terminating the process. A different approach, such as a conditional `IO.puts` or using a different looping construct, should be used.