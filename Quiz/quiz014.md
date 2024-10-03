## Paper Solution
![photo_2024-10-04_03-16-28](https://github.com/user-attachments/assets/3bf2b439-d5ec-4d77-a064-046f328676b7)
## Flow Diagram
![image](https://github.com/user-attachments/assets/167e4348-4ba7-4c01-b01e-70621f158dfa)

## Code
```.py
def open_doors(n):
    doors = [False] * n

    for student in range(1, n + 1):
        for door in range(student - 1, n, student):
            doors[door] = not doors[door]
    
    return ["open" if door else "closed" for door in doors]

n = 10
print(open_doors(n))
```
## Proof Code Works
![image](https://github.com/user-attachments/assets/8a2aa24b-8c67-4106-bb35-e6796c11fb1f)

