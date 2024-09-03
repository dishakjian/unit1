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
