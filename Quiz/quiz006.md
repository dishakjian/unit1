# Paper solution
![photo_2024-09-12_08-39-17](https://github.com/user-attachments/assets/d6d6b96d-17d3-4fb7-a8dc-5436ece8423a)

# This program will generate random secure passwords
# Code
```.py
import random

def generate_password(length, include_symbols):
    lower = 'abcdefghijklmnopqrstuvwxyz'
    upper = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'
    digits = '0123456789'
    symbols = '!@#$%^&*()-_=+[]{}|;:,.<>?/'

    all_chars = lower + upper + digits
    if include_symbols:
        all_chars += symbols

    # Ensure at least one character from each required set
    password_chars = [
        lower[random.randint(0, len(lower) - 1)],
        upper[random.randint(0, len(upper) - 1)],
        digits[random.randint(0, len(digits) - 1)]
    ]

    if include_symbols:
        password_chars.append(symbols[random.randint(0, len(symbols) - 1)])

    # Fill the rest of the password with random characters
    for _ in range(len(password_chars), length):
        password_chars.append(all_chars[random.randint(0, len(all_chars) - 1)])
    return ''.join(password_chars)

def validate_int(msg: str) -> int:
    while True:
        unsafe_data = input(msg)
        if unsafe_data.isdigit() and int(unsafe_data) >= 4:
            return int(unsafe_data)
        print("Invalid input. Please enter a number that is at least 4.")

def main():
    length = validate_int("Enter the desired password length (minimum 4): ")

    include_symbols_input = input("Include symbols? (y or n): ")
    include_symbols = include_symbols_input.lower() == 'y'

    password = generate_password(length, include_symbols)
    print("Generated Password:", password)

if __name__ == "__main__":
    main()

```
# Proof code works
![image](https://github.com/user-attachments/assets/d11b8303-5921-484f-babc-0541679982b3)
# Flow diagram
![image](https://github.com/user-attachments/assets/7b4759eb-c770-46ff-8ebd-78925abb1762)
