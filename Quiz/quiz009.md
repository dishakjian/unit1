## Paper solution


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

