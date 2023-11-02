```py
def averageLenght(words: str):
    count = 0
    count2 = 0
    for i in range (len(words)):
        count += 1
        for y in range(len(words[i])):
            count2 += 1
    print(count2/count)
averageLenght(["hello", "main"])
```<img width="138" alt="Screenshot 2023-11-02 at 11 15 24" src="https://github.com/NaomiRozenberg/unit-1/assets/142605919/4604fac2-b902-4f13-a687-f011c9dacfdb">
