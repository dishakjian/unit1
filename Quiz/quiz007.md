# Paper solution
![photo_2024-09-13_00-24-03](https://github.com/user-attachments/assets/93b3fef3-79f9-4f27-bc61-655e2c9dd43c)

# Code
```.py
def hamming(m, k, p):
    n = len(m)
    t = [-1] * (n + k)
#fill the message bits
    x = 0  #index for message bits

    for i in range(len(t)):
        if i not in p:
            t[i] = int(m[x])
            x += 1

    print("Encoded message with parity placeholders:", t)
    return t

m = '1011'
k = 3
p = [0, 1, 3]

encoded_message = hamming(m, k, p)
```
# Proof the code works
![image](https://github.com/user-attachments/assets/27c5fab8-ae10-4561-9bdb-99b54b3b5c21)
# Flow diagram
![Blank diagram (5)](https://github.com/user-attachments/assets/f55b7791-705d-462c-ab98-475e18aabdc0)
