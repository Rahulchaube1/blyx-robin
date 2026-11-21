## Convert a civil date into comparable day numbers

Returns [day number with 0001-01-01 = 1, Monday-zero weekday, day-of-year, days in month]. This is a calendar computation independent of machine locale. Invalid arguments and nonfinite results return an empty vector.

1. Open an empty file named `robin-demo.blyx`.
2. Type `blyx-robin-demo` and select **Robin — runnable example**. You can also use **Snippets: Fill File with Snippet**.
3. Choose **Blyx: Run File** from the command palette. Change an argument near the end of `fn main()` to try another input.

Expected output

```text
719163
3
1
31
```

[Work through the example in the browser](https://www.blyx-lang.space/play?example=package-robin)
