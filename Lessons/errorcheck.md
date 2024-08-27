# Code to print error bit
```.py
binary_input = input("Enter a binary code: ")
count_ones = 0

for char in binary_input:
    if char =='1':
        count_ones += 1

if count_ones % 2 == 0:
    print(f"1{binary_input}")
else:
    print(f"0{binary_input}")


```
# Proof code works
![image](https://github.com/user-attachments/assets/97af0719-340d-4a5b-a2a9-a752bcdf0378)

# Code to check error bit
```.py
binary_input = input("Enter the binary code you want to error-check:")
error_check = binary_input[0]

count_ones = 0

for char in binary_input[1:]:
    if char == '1':
        count_ones += 1

if error_check == ('1' if count_ones % 2 == 0 else '0'):
    print("No error detected.")
else:
    print("Error detected")
```
# Proof code works
![image](https://github.com/user-attachments/assets/813090b8-b4dd-45be-b63d-93d8d0f423ef)
