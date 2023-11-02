```py

def blckBoxThree(word: str):
    alphabet = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']
    count = [0] * 26  # Initialize count list with zeros for each letter
    out = ' '
    for l in word:
        if l in alphabet:
            index = alphabet.index(l)
            count[index] += 1
            out += str(count[index])
        else:
            out += " "


    print(out)

blckBoxThree('hello world')
```<img width="138" alt="Screenshot 2023-11-02 at 10 51 22" src="https://github.com/NaomiRozenberg/unit-1/assets/142605919/5564f56a-405e-4af2-aa3c-fdc5e3041614">
