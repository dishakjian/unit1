## Paper Solution
![photo_2024-10-04_03-25-58](https://github.com/user-attachments/assets/08ae9523-6bbd-4bcc-91a6-306ff29a9522)

## Flow Diagram
![image](https://github.com/user-attachments/assets/08c41350-dcc9-40fd-a2f8-64e512f0c242)

## Code
```.py
def averageLength(words):
    total_length = sum(len(word.replace(" ", "")) for word in words)
    num_words = len(words)
    if num_words == 0:
        return 0.0
    return total_length / num_words

print(averageLength(["hello", "main"]))             
print(averageLength(["Peru", "France", "Nepal"]))  
print(averageLength(["Computer Science", "Art"]))   
print(averageLength(["one", "two"]))               
```
## Proof Code Works
![image](https://github.com/user-attachments/assets/3caaf92d-c2d7-4ef5-9548-589c11fad4ca)
