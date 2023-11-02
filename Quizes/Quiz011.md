```py
def mulTable(number):
    output = ''
    if number>2 and number <10:
        for x in range (1,10):
            out = number*x
            output +=f'{number} x {x} = {out}\n'
    else:
        output = "eror"
    return output
sample = mulTable(3)
print(sample)
```<img width="138" alt="Screenshot 2023-11-02 at 10 17 37" src="https://github.com/NaomiRozenberg/unit-1/assets/142605919/3ad8e56e-d341-4030-ba38-2186c909604a">
