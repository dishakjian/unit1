## Paper solution
![photo_2024-10-04_01-27-19](https://github.com/user-attachments/assets/979773cc-c400-4e21-985e-49c7d0a4e4c6)

## Flow diagram
![Flowchart (2)](https://github.com/user-attachments/assets/89b98f87-5abc-49c0-a717-9955e33fb4be)

## Code
```.py
def convert():
    a=int(input("Enter number: "))
    unit = input("Enter unit: ")
    units =["tera", "giga", "mega", "kilo", "unit", "mili", "micro", "nano", "pico"]
    counts = 0
    for i in range(-12,13,3):
        num = a*10**i
        unit1 = units[counts]
        print(f"{num} {unit1}{unit}")
        counts +=1
convert()
```
## Proof Code Works
![image](https://github.com/user-attachments/assets/95cb8ac5-f2fc-45f0-84ba-339a73b65afb)
