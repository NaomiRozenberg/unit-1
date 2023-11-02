```py def schoolDoors(N:int):
    count = 0
    doors = [False] *N
    for student in range(1, N+1):
        for door in range(student - 1, N, student):
            doors[door] = not doors[door]
    count = sum(doors)  
    return count

sample = schoolDoors(10)
print(sample)
```<img width="138" alt="Screenshot 2023-11-02 at 11 34 42" src="https://github.com/NaomiRozenberg/unit-1/assets/142605919/60aebf4a-f0b5-4aec-8bd2-2c4f4afac0aa">
