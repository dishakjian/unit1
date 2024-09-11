# Paper solution

# This program calculates the sum of the characters in a given string using a custom character-to-value mapping. Each letter is assigned a specific value, and spaces are ignored. 
# Code
```.py

def sum_of_characters(input_text: str) -> int:
    char_values = {
        'a': 1, 'A': 1,
        'b': 2, 'B': 2,
        'c': 3, 'C': 3,
        'd': 4, 'D': 4,
        'e': 5, 'E': 5,
        'f': 6, 'F': 6,
        'g': 7, 'G': 7,
        'h': 8, 'H': 8,
        'i': 9, 'I': 9,
        'j': 10, 'J': 10,
        'k': 11, 'K': 11,
        'l': 12, 'L': 12,
        'm': 13, 'M': 13,
        'n': 14, 'N': 14,
        'o': 15, 'O': 15,
        'p': 16, 'P': 16,
        'q': 17, 'Q': 17,
        'r': 18, 'R': 18,
        's': 19, 'S': 19,
        't': 20, 'T': 20,
        'u': 21, 'U': 21,
        'v': 22, 'V': 22,
        'w': 23, 'W': 23,
        'x': 24, 'X': 24,
        'y': 25, 'Y': 25,
        'z': 26, 'Z': 26,
        ' ': 0  # Space has no value
    }

    total_sum = 0

    for char in input_text:
        total_sum += char_values.get(char, 0)

    return total_sum


print(sum_of_characters("Math"))
print(sum_of_characters("maTH"))
print(sum_of_characters("Hello world"))
print(sum_of_characters("Computer SCIENCE"))
```
# Proof code works
![image](https://github.com/user-attachments/assets/812712b3-6107-4466-a81d-09ed040b6758)
