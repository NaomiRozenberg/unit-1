```py
def summ_letters(text:str)->int:
    alphbet= "abcdefghijklmnopqrstuvwxyz"
    sum = 0
    for let in text.lower():
        index =-1
        for i in range(len(alphbet)):
            if let == alphbet[i]:
                index = i + 1
        sum += index
    return sum
#proof of work
case1 = summ_letters(text="Math")
print(case1)
case2 = summ_letters(text="maTH")
print(case2)
case3 = summ_letters(text="Hello world")
print(case3)
case4 = summ_letters(text="Computer Science")
print(case4)
```
<img width="276" alt="Screenshot 2023-09-12 at 12 51 27" src="https://github.com/NaomiRozenberg/unit-1/assets/142605919/3dfdd725-24ee-4f84-b9e3-ba5780d9d503">
<img width="520" alt="Screenshot 2023-09-12 at 13 00 02" src="https://github.com/NaomiRozenberg/unit-1/assets/142605919/c55a3a75-92d5-4156-9070-d7057ebb15e6">
