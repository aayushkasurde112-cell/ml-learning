## Mistake: Understanding `for...else` and `break`

### ❌ My Mistake
I thought that since `else` is written outside the `for` loop's body, it would always execute after the loop, even if `break` was used.

### ✅ Correct Understanding
- In Python, `else` is **attached to the `for` loop**, not outside of it.
- `break` exits only the loop, but it also **prevents the `for...else` block from running**.
- If the loop completes all iterations normally (without `break`), then the `else` block executes.

### Rule to Remember
- `break` → Exit the nearest loop and skip the `for...else`.
- `continue` → Skip the current iteration.
- `return` → Exit the entire function.
