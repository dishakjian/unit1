# Program description
This code takes three heights in centimeters, sorts them in descending order, and prints them from largest to smallest.

# Code
```.py
height1 = float(input("Enter the first height in cm: "))
height2 = float(input("Enter the second height in cm: "))
height3 = float(input("Enter the third height in cm: "))

heights = [height1, height2, height3]

heights.sort(reverse=True)

print("Heights from largest to smallest:")
for height in heights:
    print(f"{height} cm")
```
