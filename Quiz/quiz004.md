# Program description
This code prompts the user to input a number, validates that the input is a valid positive integer, and then finds all the factors of the number. It also checks if the number is a perfect number, which is a number equal to the sum of its proper divisors (excluding the number itself). The code then outputs the list of factors and whether the number is a perfect number (True or False).
# Code
```.py
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

# Check if the number is a perfect number
# A perfect number is equal to the sum of its proper divisors (excluding itself)
sum_of_proper_divisors = sum(factors[:-1])
is_perfect = sum_of_proper_divisors == num

print(f"Factors of {num} are: {factors}")
print(f"Is {num} a perfect number? {is_perfect}")
```
# Proof code works
![image](https://github.com/user-attachments/assets/d535fb4b-0c65-4fc2-8cc7-a8f65674c6f7)

# Flow diagram
![Blank diagram (3)](https://github.com/user-attachments/assets/9434fbd7-326a-4f3a-b654-19d3be21e4f0)

