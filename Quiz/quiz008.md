# Paper solution
N/A - wasn't present

# Code
## SL
```.py
def get_room_details(room_number):
    floor = (room_number - 1) // 10 + 1
    room_on_floor = (room_number - 1) % 10 + 1

    room_name = f"{room_number}-Room {floor}F{room_on_floor:02}"

    print(room_name)

for room in range(1, 101):
    get_room_details(room)
```
## HL
```.py
def print_room_details(room_number):
    floor = (room_number - 1) // 10 + 1
    room_on_floor = (room_number - 1) % 10 + 1

    print(f"Room {floor}F{room_on_floor:02}")


print_room_details(25)
```
# Proof code works
## SL
![image](https://github.com/user-attachments/assets/ba6c38ff-454d-4489-a91b-3be248216ed1)

## HL 
![image](https://github.com/user-attachments/assets/25deaed6-507f-447c-96ee-f7a7d5f7c0e8)
