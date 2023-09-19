# Documentation

## Step 1 - Codeblocks

Codeblocks in a nutshell makes it *very easy* for **people** to ***copy, paste and share code.*** We use this whenever possible.

##As an example:

def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n - 1)

num = int(input("Enter a number: "))

if num < 0:
    print("Factorial is not defined for negative numbers.")
else:
    result = factorial(num)
    print(f"The factorial of {num} is {result}")
