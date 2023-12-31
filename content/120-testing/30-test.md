+++
+++

{{% section %}}

# Table-Driven Testing 🪑🍽️

---
#### Table-Driven Testing
- Table-Driven Testing is a technique in which test cases are defined in a table-like structure.
- Instead of writing individual test functions for each scenario, a single test function is used to iterate over the table of test cases.
- Each row in the table represents a specific test case, with inputs and expected outputs defined.

---
#### Benefits of Table-Driven Testing

- Enables concise and organized test code.
- Facilitates easy addition and modification of test cases.
- Enhances test coverage by covering various scenarios through a single test function.
- Promotes test code reusability and maintainability.

---

- Example: Testing a mathematical function, `Add`, that takes two integers and returns their sum.
- The table includes test cases with different inputs and expected outputs:

| Input   | Expected Output |
|---------|-----------------|
| 2, 3    | 5               |
| -1, 5   | 4               |
| 0, 0    | 0               |

- The test function iterates over the table, calling `Add` with each input and checking if the returned value matches the expected output.

---

```go
testCases := []struct {
		a, b     int
		expected int
	}{
		{2, 3, 5},    // Test Case 1: 2 + 3 = 5
		{-5, 10, 5},  // Test Case 2: -5 + 10 = 5
		{0, 0, 0},    // Test Case 3: 0 + 0 = 0
		{100, -100, 0}, // Test Case 4: 100 + (-100) = 0
	}

	for _, tc := range testCases {
		result := Add(tc.a, tc.b)
		if result != tc.expected {
			t.Errorf("Add(%d, %d) = %d, expected %d", tc.a, tc.b, result, tc.expected)
		}
	}
```

---
# Exercise 🏋️‍♀️

```shell
cd 120-testing/03-table
```

{{% /section %}}