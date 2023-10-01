
table= ' '
number =3
def mulTable(number):
    if number>2 and number <10:
        for x in range (1,10):
            out = number*x
            table += f"{number} X {x} = {out}"
            return table
    else:
        return "eror"
print(mulTable)
