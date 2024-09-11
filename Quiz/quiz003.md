# Paper solution
![photo_2024-09-12_08-36-30](https://github.com/user-attachments/assets/ba251ced-dda9-4ac2-bf93-a1c67d27aecc)

# Program description
This code converts a DNA sequence into its complementary sequence.
# SL
```.py
in_protein = str(input("enter a DNA protein: "))
if in_protein == "A":
    out_protein = "T"
elif in_protein == "T":
        out_protein = "A"
elif in_protein == "C":
        out_protein = "G"
elif in_protein == "G":
        out_protein = "C"
print(out_protein)
```
# HL
```.py
dictDNA = {"A":"T","G":"C", "T":"A", "C":"G"}

def is_valid_dna(sequence):
    valid_bases = {"A", "G", "T", "C"}
    return all(base in valid_bases for base in sequence)

in_protein = input("Enter a DNA sequence (only A, G, T, C): ").upper()

while not is_valid_dna(in_protein):
    print("Invalid input. Please enter a sequence containing only A, G, T, and C.")
    in_protein = input("Enter a DNA sequence (only A, G, T, C): ").upper()

out_protein = ""
for i in range(len(in_protein)):
    out_protein += dictDNA[in_protein[i]]
print("Complementary sequence:", out_protein)

```
# Flow diagram
![Blank diagram (2)](https://github.com/user-attachments/assets/c08058d9-6bbd-430d-a740-6ee1f608800b)

