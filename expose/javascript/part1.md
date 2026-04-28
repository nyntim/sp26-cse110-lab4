# Part 1 - Variables & Scoping

1. `values added:  20`
2. `final result:  20`
3. `var` is function-scoped rather than block-scoped, so it leaks outside the `if` block where it was declared. This can cause naming conflicts and unexpected access to variables outside their intended scope. `let` and `const` are block-scoped and more predictable.
4. `values added:  20`
5. ReferenceError: result is not defined — `let` is block-scoped, so `result` is not accessible outside the `if` block.
6. TypeError: Assignment to constant variable — `const` cannot be reassigned, so the error is thrown at the reassignment (`result = num1 + num2`) before line 9 is reached.
7. The TypeError from Q6 prevents execution from reaching line 13, so nothing is printed.
