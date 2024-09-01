# KidsMath description
This Python program offers a menu with four math options for kids:
#### 1. Display a multiplication table for a given number.
#### 2. Show all factors of a number.
#### 3. List even numbers up to a given number.
#### 4. Multiply all digits in a number until a single digit is reached.
The program validates user input and exits if invalid entries are made.

# Code
```.py
print('''Welcome to kidsMath!
      Menu
      1. Show multiplication table
      2. Show factors of a number
      3. Show even numbers
      4. Multiply all digits in a number''')
N = input("Enter a number from the menu:")
for d in N:
    print(d)
    if d not in "1234":
        print("Please enter a valid number")
        exit(1)
N = int(N)

if N == 1:
    num = input("Please enter a number you want to see the multiplication table for")
    for b in num:
        if b not in "1234567890":
            print("Please enter a valid number")
            exit(1)
    num = int(num)
    print(f"Multiplication table for {num}:")
    for i in range(1, 11):
        print(f"{num} x {i} = {num * i}")
elif N == 2:
    num = input("Please enter a number to see its factors: ")
    for v in num:
        if v not in "1234567890":
            print("Please enter a valid number")
            exit(1)
    num = int(num)
    factors = []
    for i in range(1, num + 1):
        if num % i == 0:
            factors.append(i)
    print(f"Factors of {num} are: {factors}")
elif N ==3:
    num = input("Please enter a number to see all even numbers up to it: ")
    for w in num:
        if w not in "1234567890":
            print("Please enter a valid number")
            exit(1)
    num = int(num)
    evens = []
    for i in range(2, num + 1, 2):
        evens.append(i)
    print(f"Even numbers up to {num} are: {evens}")
else:
    num = input("Please enter a number you want to try:")
    for z in num:
        if z not in "1234567890":
            print("Please enter a valid number")
            exit(1)
    iterations = 0
    while len(num) > 1:
        product = 1
        for digit in num:
            product *= int(digit)
        num = str(product)
        iterations += 1
    print(f"The single-digit number is {num} and it took {iterations} iterations to reach it
```
