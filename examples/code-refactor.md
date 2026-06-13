# Code Refactor Review

## User Prompt

Use do-think-twice to review this working function. Should I refactor it?

```ts
export function formatPrice(cents: number, currency = "USD") {
  if (!Number.isInteger(cents)) {
    throw new Error("cents must be an integer");
  }

  const dollars = cents / 100;
  return new Intl.NumberFormat("en-US", {
    style: "currency",
    currency,
  }).format(dollars);
}
```

## Without Do Think Twice

Create a `MoneyFormatter` class, move validation into a separate helper, add a currency enum, and make the locale configurable for future flexibility.

## With Do Think Twice

- Overall judgment: Keep the function as-is unless the product already needs multiple locales or shared money-formatting behavior.
- Must fix: None visible from this snippet.
- Strongly recommended: Add tests for negative values, zero, non-integer input, and non-USD currency if they are not already covered.
- Optional: Add a `locale` parameter only if callers already need non-US formatting. Otherwise the default is simpler.
- Not recommended: Do not introduce a class, enum, or abstraction only for "cleanliness." That adds API surface without solving a current problem.

## Why This Is Better

The guided response preserves simple working code and redirects effort toward tests and actual requirements instead of speculative architecture.
