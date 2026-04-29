**1.** Prints `3`. `var` is function-scoped, not block-scoped, so `i` remains accessible after the loop ends. The loop incremented `i` to 3 before the condition `i < prices.length` failed.

**2.** Prints `150`. `var discountedPrice` is function-scoped, so it persists after the loop. Its last assigned value was `300 * (1 - 0.5) = 150`.

**3.** Prints `150`. `var finalPrice` is function-scoped and was last set to `Math.round(150 * 100) / 100 = 150`.

**4.** Returns `[50, 100, 150]`. The loop computes the discounted price for each element and pushes the rounded value into `discounted`, which is then returned.

**5.** Throws `ReferenceError: i is not defined`. `let i` is block-scoped to the `for` loop, so it does not exist outside of it.

**6.** Throws `ReferenceError: discountedPrice is not defined`. `let discountedPrice` is block-scoped to the loop body and is inaccessible outside.

**7.** Prints `150`. `let finalPrice` is declared in the function scope (outside the loop), so it remains accessible. Its last value was `150`.

**8.** Throws a `ReferenceError` at line 12 (the `console.log(i)` call) before the function can return. The function never reaches the `return` statement.

**9.** Throws `ReferenceError: i is not defined`. `let i` is block-scoped to the `for` loop and does not exist outside it.

**10.** Never reached because line 11 throws a `ReferenceError`. If it were reached, it would print `3` since `const length = prices.length` is function-scoped and equals 3.

**11.** Throws a `ReferenceError` at line 11. The function never reaches the `return` statement.

**12a.** `student.name`

**12b.** `student['Grad Year']`

**12c.** `student.greeting()`

**12d.** `student['Favorite Teacher'].name`

**12e.** `student.courseLoad[0]`

**13a.** `'32'` — The `+` operator with a string triggers string concatenation, so `2` is coerced to `'2'` and appended.

**13b.** `1` — The `-` operator has no string behavior, so `'3'` is coerced to the number `3`, giving `3 - 2 = 1`.

**13c.** `3` — `null` coerces to `0` in numeric context, so `3 + 0 = 3`.

**13d.** `'3null'` — The `+` operator with a string coerces `null` to the string `'null'` and concatenates.

**13e.** `4` — `true` coerces to `1` in numeric context, so `1 + 3 = 4`.

**13f.** `0` — `false` coerces to `0` and `null` coerces to `0`, so `0 + 0 = 0`.

**13g.** `'3undefined'` — The `+` operator with a string coerces `undefined` to the string `'undefined'` and concatenates.

**13h.** `NaN` — The `-` operator coerces `'3'` to `3` and `undefined` to `NaN`; any arithmetic with `NaN` produces `NaN`.

**14a.** `true` — `'2'` is coerced to the number `2`, and `2 > 1` is `true`.

**14b.** `false` — Both operands are strings, so comparison is lexicographic. `'2'` is compared character-by-character with `'12'`; `'2'` > `'1'`, so `'2' < '12'` is `false`.

**14c.** `true` — `==` performs type coercion; `'2'` is coerced to `2`, so `2 == 2` is `true`.

**14d.** `false` — `===` checks both value and type with no coercion. `2` (number) and `'2'` (string) are different types.

**14e.** `false` — `true` coerces to `1`, and `1 == 2` is `false`.

**14f.** `true` — `Boolean(2)` evaluates to `true` (any non-zero number is truthy). `true === true` is `true`.

**15.** `==` is the loose equality operator: it performs type coercion before comparing, so operands of different types may be converted to a common type first. `===` is the strict equality operator: it compares both value and type with no coercion, returning `false` if the types differ.

**16.** See `part2-question16.js`

**17.** Returns `[2, 4, 6]`. `modifyArray` iterates over `[1, 2, 3]` and calls `doSomething` on each element, which multiplies it by 2. So `1 → 2`, `2 → 4`, `3 → 6`, and those results are pushed into `newArr`.

**18.** See `part2-question18.js`

**19.** The output is `1`, `4`, `3`, `2`. `console.log(1)` and `console.log(4)` run synchronously in order. Both `setTimeout` callbacks are deferred to the event queue; the 0ms timeout fires after the current synchronous code finishes (printing `3`), and the 1000ms timeout fires last (printing `2`).
