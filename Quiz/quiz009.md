## Paper solution
![photo_2024-10-04_01-23-21](https://github.com/user-attachments/assets/91109faa-4e00-46d1-b7ec-263ebc1f2ba7)


## Flow diagram
![Flowchart](https://github.com/user-attachments/assets/629f8408-33c2-4d79-8133-57d6d48b3a6c)

## Code
```.py
def cipher(input_string, shift):
    alphabet_lower = "abcdefghijklmnopqrstuvwxyz"
    alphabet_upper = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"

    result = ""

    for char in input_string:
        if char in alphabet_lower:
            index = alphabet_lower.index(char)
            result += alphabet_lower[(index + shift) % 26]
        elif char in alphabet_upper:
            index = alphabet_upper.index(char)
            result += alphabet_upper[(index + shift) % 26]
        else:
            result += char
    return result

input_string = "Hello, World!"
shift = 13
ciphered = cipher(input_string, shift)
print(ciphered)

```

## Proof code works
![image](https://github.com/user-attachments/assets/987e2165-f67b-4a55-b8ed-43363701bed6)

