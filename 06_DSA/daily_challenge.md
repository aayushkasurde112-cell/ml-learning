# Problem 1833  
https://leetcode.com/problems/maximum-ice-cream-bars/

## DSA Note: `break` vs `return` Inside a Loop

I used the following code:

```python
costs.sort()
total = 0

for i in range(len(costs)):
    total += costs[i]
    if total > coins:
        break

return i
```

## Observation

- `i` is the **current index**, **not** the number of ice creams bought.
- When the purchase fails at index `i`, I have successfully bought the first `i` ice creams (indices `0` to `i-1`).
- Therefore, returning `i` after a `break` gives the correct answer **only when the loop breaks**.

## Edge Case

If I can afford **all** the ice creams, the loop never breaks.

Example:

```python
costs = [1, 1, 2, 3, 5, 6]
coins = 20
```

Loop finishes with:

```python
i = 5
```

But I have bought **6** ice creams.

So:

```python
return i      # ❌ Returns 5
return len(costs)  # ✅ Returns 6
```

## Correct Pattern

```python
costs.sort()
total = 0

for i in range(len(costs)):
    total += costs[i]
    if total > coins:
        return i

return len(costs)
```

## Key Learning

- `break` exits the loop but execution continues after the loop.
- `return` immediately exits the function.
- Always consider the **"loop never breaks"** edge case when using `break`.
- Ask yourself:
  > "What happens if every iteration succeeds?"
