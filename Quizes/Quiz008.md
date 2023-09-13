```py
digit = int(input("Type a digit "))

unites = ['tera','Giga','Mega','kilo']
powers =[12,9,6,3]
output = ''
for x in range (len(unites)):
    output +=f'{digit}{"0"*powers[x]} {unites[x]}\n'

output2 = ''
unites2 = ['Mili','Micro','Nano','Pico']
powers2 =[2,5,8,11]
for y in range (len(unites2)):
    output2 +=f'0.{"0"*powers2[y]}{digit} {unites2[y]}\n'

print(f"{output}{digit}\n{output2}")
```
<img width="256" alt="Screenshot 2023-09-13 at 11 00 12" src="https://github.com/NaomiRozenberg/unit-1/assets/142605919/d44e8880-94ad-41e3-9efa-a42c5a7cb1e4">
