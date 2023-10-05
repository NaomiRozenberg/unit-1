```py
import requests

print("Welcome to The Crypto wallet!".center(100))
# login
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
while result == False and attempts >0:
    name = input("EROR Enter your username ")
    password = input("EROR Enter your password ")
    result = try_login(name=name, password=password)
    attempts -= 1
if result == False:
    print(f"Exiting...")
else:
    print(f"Welcome {name}")

#menu
options = ['Statistics','Value of TRON','Recnt Instegram posts by TRON ', "Update Your information"]
menu =int(input(f"what would you like to view?\n1. {options[0]} \n2. {options[1]} \n3. {options[2]}\n4. {options[3]}\n\nEnter (1-4) "))
while menu != 1 and menu != 2 and menu != 3 and menu != 4:
    menu =int(input("Please enter a number between 1 - 4 "))
#stats
if menu == 1:
    spending = 0
    monthly_income = 0
    with open("user.csv", 'r') as f:
        data1 = f.readlines()
        for line in data1:
            if name == line.split(',')[0]:
                monthly_income = line.split(',')[3]
                spending = line.split(',')[4]
        import matplotlib.pyplot as plt

        activities = ['Spending', 'Savings']
        spending = int(spending)
        monthly_income = int(monthly_income)
        slices = [spending, monthly_income - spending]
        colors = ['r', 'y']
        plt.pie(slices, labels=activities, colors=colors,
                startangle=90, shadow=True, explode=(0, 0),
                radius=1.2, autopct='%1.1f%%')
        plt.legend()
        plt.show()
#value
if menu == 2:
    import requests
    def get_tron_price_in_jpy():
        url = "https://api.coingecko.com/api/v3/simple/price"
        params = {'ids': 'tron','vs_currencies': 'jpy'}

        try:
            response = requests.get(url, params=params)
            response.raise_for_status()
            data = response.json()
            tron_price_jpy = data['tron']['jpy']
            return tron_price_jpy
        except requests.exceptions.RequestException as e:
            print(f"Error fetching TRON price in JPY: {e}")
            return None

    if __name__ == "__main__":
        tron_price_jpy = get_tron_price_in_jpy()
        if tron_price_jpy is not None:
            print(f"The current value of TRON in JPY is ¥{tron_price_jpy}")
        else:
            print("Failed to retrieve TRON price in JPY.")
#facebook
if menu == 3:
    import facebook
    def get_facebook_page_posts(page_id, access_token, count=5):
        graph = facebook.GraphAPI(access_token)
        try:
            posts = graph.get_object(f'{page_id}/posts', fields='id,message,created_time', limit=count)
            return posts.get('data', [])
        except facebook.GraphAPIError as e:
            print(f"Error fetching Facebook posts: {e}")
            return None
    if __name__ == "__main__":
        page_id = '144555002795817'
        access_token = 'EAAljStb9XqEBO41ecgu5MZAcik0ZCNtYQgmyjULRGh4DHOn0eXdBRoNIZCtZBZCZBAoTVwzZA80cpmAz5yZAol0RgfaCy7IapI0CADB2dcH3cLmMZCNvUJgHT4nnuak6b8mssFzj4GeapK3IYKKQPAPwnNlDxvWQ41Uxhl1QnAHizSDH3YmSsT7gk9N6gEeFJEb2Dlo6wylSklXefMslzcMoleZCSlCjcOYrN4zLZAWNnntmlLODyIMIWQvF8TtybTfVgZDZD'
        recent_posts = get_facebook_page_posts(page_id, access_token)
        print(recent_posts)
        if recent_posts is not None:
            for post in recent_posts:
                print(f"Post ID: {post['id']}")
                print(f"Message: {post.get('message', 'No message')}")
                print(f"Created Time: {post['created_time']}")
                print("\n")
        else:
            print("Failed to retrieve recent posts.")
#info
if menu == 4:
    with open("user.csv", 'r') as f:
        data1 = f.readlines()
        for line in data1:
            if name == line.split(',')[0]:
                monthly_income = line.split(',')[3]
                amount_tron = line.split(',')[2]
    print(
        f"Below Is your current info on the site\n\n1.Name:{name}\n2.Monthly Income: {monthly_income}¥\n3.TRON:{amount_tron}")
```
