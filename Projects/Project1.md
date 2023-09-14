# Crypto Wallet

![](22ROOSE-master768.gif)  
<sub>Illustration for Glenn Harvey</sub>

# Criteria A: Planning

## Problem definition

Ms. Sato is a local trader who is interested in the emerging market of cryptocurrencies. She has started to buy and sell electronic currencies, however at the moment she is tracking all his transaction using a ledger in a spreadsheet which is starting to become burdensome and too disorganized. It is also difficult for Ms Sato to find past transactions or important statistics about the currency. Ms Sato is in need of a digital ledger that helps her track the amount of the cryptocurrency, the transactions, along with useful statistics. 

Apart for this requirements, Ms Sato is open to explore a cryptocurrency selected by the developer.
An example of the data stored is 

| Date | Description | Category | Amount  |
|------|-------------|----------|---------|
| Sep 23 2022 | bought a house | Expenses | 10 BTC |
| Sep 24 2022 | food for house celebration | Food | 0.000001 BTC |


## Proposed Solution

Design statement:
I will to design and make a ———— for a client who is ———. The ——– will about ———— and is constructed using the software ———. It will take  ———- to make and will be evaluated according to the criteria ———.

** add a description of your coin and citation **

Justify the tools/structure of your solution

## Success Criteria
1. The electronic ledger is a text-based software (Runs in the Terminal).
2. The electronic ledger display the basic description of the cyrptocurrency selected.
3. The electronic ledger allows to enter, withdraw and record transactions.
4. The electronic ledger provides real time value of currency.
5. The electronic ledger requires a password for access.
6. The electronic ledger shows statistics such as: cash balnce and value of currency over time. 


# Criteria B: Design

## System Diagram

## Flow Diagrams


## Record of Tasks
| Task No | Planned Action                          | Planned Outcome                                                                          | Time estimate | Target completion date | Criterion |
|:-------:|-----------------------------------------|------------------------------------------------------------------------------------------|---------------|------------------------|-----------|
|    1    | Create system diagram                   | To have a clear idea of the hardware and software requirements for the proposed solution | 10min         | Sep 24                 | B         |
|    2    | Create Flow diageam for login functions |                                                                                          |               |                        |           |
|    3    |                                         |                                                                                          |               |                        |           |

# Criteria C: Development

## Login System
My client requires a system to protect the private data. I thought about using a login system to accomplish this requirement using a if condition and the open command to work with a csv file. More description of the code... 
```.py
def try_login(name:str, password:str)->bool:
    with open("user.csv", mode ='r') as f:
        data = f.readlines()
    logged_in = False
    for line in data:
        uname = line.split(',')[0]
        upass = line.split(',')[1].strip()
        if uname == name and upass==password:
            logged_in = True
            break
    return logged_in
attempts = 3
name = input("Enter your username ")
password = input("Enter your password ")
result = try_login(name=name, password=password)
print(result)
while result == False and attempts >0:
    name = input("EROR Enter your username ")
    password = input("EROR Enter your password ")
    result = try_login(name=name, password=password)
    attempts -= 1
if result == False:
    print(f"Exiting...")
else:
    print(f"Welcome {name}")
```

```

