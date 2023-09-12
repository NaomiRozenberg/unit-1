``` py
def DNA_transletor(in_protein:str ):

    if in_protein in "ATCG":
         if in_protein == "A":
            out_protein= "T"
         if in_protein == "G":
            out_protein= "C"
         if in_protein == "T":
            out_protein= "A"
         if in_protein == "C":
            out_protein= "G"
    else:
        return "[error]"

    return out_protein
def translateSequence (sequence:str):
    output_sequence = ""
    for p in sequence:
        print(p)
        output_sequence += DNA_transletor(in_protein=p)
        print(output_sequence)
case1= DNA_transletor(in_protein=input("enter a string "))
print(case1)
```
<img width="344" alt="Screenshot 2023-09-12 at 11 20 58" src="https://github.com/NaomiRozenberg/unit-1/assets/142605919/105093c0-65d1-4bf3-a4e4-46191e3c190c">

