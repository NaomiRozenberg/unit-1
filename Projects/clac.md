```py
name = 'alice'
spending = 0
monthly_income = 0
with open("user.csv", 'r') as f:
	data1 = f.readlines()
	for line in data1:
		if name == line.split(',')[0]:
			monthly_income = line.split(',')[3]
			spending = line.split(',')[4]
	import matplotlib.pyplot as plt
	activities = ['Spending','Savings']
	spending = int(spending)
	monthly_income = int(monthly_income)
	print(monthly_income)
	print(spending)
	print(spending/monthly_income*100)
	slices = [spending, monthly_income-spending]
	colors = ['r', 'y']
	plt.pie(slices, labels = activities, colors=colors,
			startangle=90, shadow = True, explode = (0, 0),
			radius = 1.2, autopct = '%1.1f%%')
	plt.legend()
	plt.show()
```
