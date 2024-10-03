## Paper Solution
![photo_2024-10-04_03-39-35](https://github.com/user-attachments/assets/962f14d1-82a6-46ca-b62c-ff485430a7e9)

## Flow Diagram
![image](https://github.com/user-attachments/assets/52e3cec7-da43-43b1-8a8b-4afc8f708db3)

## Boolean Circuit
AB + not(B + C) + B(notC notA)
AB + notB notC + B(notC notA)
AB + notC(B notA + notB)

## Code
```.py
def get_l3tt3r(msg: str) -> str:
    replacements = {
        'a': '4', 'e': '3', 'i': '1', 'o': '0', 
        'A': '4', 'E': '3', 'I': '1', 'O': '0', 
        ' ': '_'
    }
    
    return ''.join(replacements.get(char, char) for char in msg)

case1 = get_l3tt3r("Hello World")
print(case1)  

case2 = get_l3tt3r("Why did I choose CS?")
print(case2)  

case3 = get_l3tt3r("Remember the Figure Caption")
print(case3)
```
## Proof Code Works
![image](https://github.com/user-attachments/assets/43d5062c-dce2-4799-aecb-9eafdf061112)
