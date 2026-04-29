# DevTools Part 2 - Debugging

1. document.getElementById().value always returns a string, not a number. So when calculateSum(num1, num2) runs let result = num1 + num2, JavaScript sees two strings ("2" and "3") and performs string concatenation instead of numeric addition — giving "23" instead of 5. The Watch panel confirms this: typeof result is "string".

2. Convert the inputs to numbers before adding. Number() converts the string values "2" and "3" to actual numbers, so + performs arithmetic addition and returns 5 correctly.