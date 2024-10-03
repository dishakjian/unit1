## Paper Solution
![photo_2024-10-04_02-57-23](https://github.com/user-attachments/assets/c061f705-cce1-42ed-9a55-c92f0c1b796a)

## Flow diagram
![Flowchart (3)](https://github.com/user-attachments/assets/e7e91728-e79d-49cf-a387-29b1fac0479c)

## Code
```.py
month = int(input("Enter your month number (1-12): "))
days_of_week = ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"]
start_day = [0, 3, 3, 6, 1, 4, 6, 2, 5, 0, 3, 5]
day_month = [31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
days_in_month = day_month[month - 1]
first_day = start_day[month - 1]

calendar = '  '.join(days_of_week) + '\n'
calendar += '    ' * first_day
day_counter = 1
while day_counter <= days_in_month:
    calendar += f"{day_counter:2}  "
    first_day += 1
    day_counter += 1
    if first_day == 7:
        calendar += '\n'
        first_day = 0 
print(calendar)
```
## Proof Code Works
![image](https://github.com/user-attachments/assets/6e9bbfbb-0250-40d1-aa4d-a370890e7861)
