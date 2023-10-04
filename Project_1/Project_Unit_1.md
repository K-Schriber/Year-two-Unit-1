# Crypto Wallet


 ![ether-reach-the-ether](https://github.com/K-Schriber/Unit-1-Comp-Sci/assets/142757998/91d4c72d-feee-4aec-9861-aa653dfd6424)

<sub>Ethereum GIF by ethmemes</sub>

# Criteria A: Planning

## Problem definition

Ms. Sato is a local trader who is interested in the emerging market of cryptocurrencies. She has started to buy and sell electronic currencies, however at the moment she is tracking all his transaction using a ledger in a spreadsheet which is starting to become burdensome and too disorganized. It is also difficult for Ms Sato to find past transactions or important statistics about the currency. Ms Sato is in need of a digital ledger that helps her track the amount of the cryptocurrency, the transactions, along with useful statistics. 

Apart for this requirements, Ms Sato is open to explore a cryptocurrency selected by the developer.

An example of the data stored is 

| Date | Description | Category | Amount  |
|------|-------------|----------|---------|
| Sep 23 2022 | bought a house | Expenses | 10 BTC |
| Sep 24 2022 | food for house celebration | Food | 0.000001 BTC |




## Design statement:
I will to design and make a Ethruuen Wallet for a client who is trying to set up an acounnt. The wallet will hold currency and is constructed using the software pyhton. It will take  30 days to make and will be evaluated according to the criteria (please check succes critera 1-6).

## Rationale for Proposed Solution
I chose Python because it’s one of the most user-friendly programming languages that is quickly growing globally. [1] According to Linked In, python is easy to understand because of its simple English syntax that allows the programmer to create programs easily.[2] Python also has access to numerous libraries that allow developers to program more efficiently. These libraries provide an API (application programming interface) which makes it easy for developers to use them with their own software programs.[3] Furthermore, Pythons is versatile language that can be used for web development, software development, scientific computing, data analysis, artificial intelligence, and more.[4] Thats why I believe Python will be able to solve all of my client's problems and let her have a functioning crypto wallet.



## Description of Ethereum
** Ethereum (ETH) is a decentralized blockchain network powered by the Ether token. It enables users to transact, earn interest on their holdings through staking, use and store nonfungible tokens (NFTs), and trade cryptocurrencies. [5] Ethereum is a global platform that uses a digital ledger through multiple computers to maintain a secure and decentralized record of transactions.[6] The growth of Ethereum is expected to continue due to its widespread adoption as a platform with ongoing technological advancements, increased institutional interest, and a growing ecosystem of innovative projects; Ethereum's value is likely to rise because of its central role in the evolving landscape of decentralized finance and digital assets.[7] **


## Success Criteria
1. The electronic ledger is a text-based software (Runs in the Terminal).
2. The electronic ledger display the basic description of the cyrptocurrency selected.
3. The electronic ledger allows to enter, withdraw and record transactions.
4. The elctronic ledger displays current rate of coin
5. Login and Logout of Account
6. User can Graph Tranactions and Withdraws

# Criteria B: Design

## System Diagram

![Comp-14](https://github.com/K-Schriber/Unit-1-Comp-Sci/assets/142757998/94754c10-0cd8-4a11-93dd-248a4752fc79)
Fig 1. System diagram for the program. It shows input devices and output devices along with the sytem requirments to run the program through Python. Takes data from librarys and utilizes csv files.


## Flow Diagrams

![Comp-17](https://github.com/K-Schriber/Unit-1-Comp-Sci/assets/142757998/270975f2-a81f-4465-af81-638d68a40253)
Fig 2. The flow diagram shows how the library Requests takes the HTML code from the website then the library BeautifulSoup takes the HTML code from the library HTML5lib and then BeautifulSoup takes the individual variable that displays our current rate of Etheruem from the website and prints it. User gets a current rate of 1 Ethereum.

![Comp-15](https://github.com/K-Schriber/Unit-1-Comp-Sci/assets/142757998/6535d9a4-a283-4fd2-a92b-bc81d511d8ae)
Fig 3. The flow diagram shows the balance system for the program. It takes lines from Transactions.csv file and takes the sum of both withdrawl and depsoti transcations. Then displays sum with the current date.

![Comp-16](https://github.com/K-Schriber/Unit-1-Comp-Sci/assets/142757998/155aff9b-a4d7-4389-984c-4eb0de095da5)
Fig 4. The flow diagram shows the Withdraw and Deposit functions. When the user witdraws or deposits into the Etheruem wallet it records the data in a Transactions.csv file that shows date, amount, and reason for transcation.

## Record of Tasks| Task No | Planned Action                               | Planned Outcome                                                                                                                                                  | Time estimate | Target completion date | Criterion |
|---------|----------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|------------------------|-----------|
| 1       | Create system diagram                        | To have a clear idea of the hardware and software requirements for the proposed solution                                                                         | 10 min        | Sep 24                 | B         |
| 2       | Create a Login System                        | To have a way for the user to login to account and logout of account.                                                                                            | 30 min        | Sep 14                 | C         |
| 3       | Check With Client                            | The client either approves six proposed ideas or denies them.(APPROVED)                                                                                          | 15 min        | Sep 18                 | A         |
| 4       | Code Menu Option                             | To have a way for the user to choose different options from the menu. Enters number 1 - 6 : Example(1 is entered and a description of the coin is in the ledger) | 40 min        | Sep 20                 | C         |
| 5       | Deposit function                             | To have the user deposit Ethuruem into the wallet he user can deposit funds to balance and allocate reason for deposit.                                          | 30 min        | Sep 20                 | C         |
| 6       | Balance function                             | User can check balance with current date                                                                                                                         | 20 min        | Sep 20                 | B,C       |
| 7       | Tweak to Deposit function                    | Stops user from depositing negative numbers to tweak balance                                                                                                     | 35 min        | Sep 23                 | B,C       |
| 8       | Create better banner                         | So the user is greeted with an eye appealing banner to welcome them to the wallet.                                                                               | 10 min        | Sep 23                 | C         |
| 9       | Rework system Diagram                        | Update with Librarys used and csv files used                                                                                                                     | 5 min         | Sep 23                 | B         |
| 10      | Withdraw Function                            | To have a way for the user to withdraw money from the account                                                                                                    | 40 min        | Sep 23                 | C         |
| 11      | Description of Coin                          | To have the user understand what the coin is with a basic description                                                                                            | 20 min        | Sep 25                 | B,C       |
| 12      | Data Web Scraper                             | To have a way for the user to check the current rate of Ethereum                                                                                                 | 120 min       | Sep 26                 | A,C       |
| 13      | Bar Graph Maker                              | To have a way fro the user to graph Transactions and Deposits                                                                                                    | 40 min        | Sep 27                 | C         |
| 14      | Write descriptions for each part of the code | So the user can see each section of the code and how it runs individually                                                                                        | 70 min        | Sep 28                 | C         |
| 15      | Video                                        | To show that the program works as a whole                                                                                                                        | 10 min        | Sep 29                 | C         |
| 16      | Test Plan Table                              | Create Test plan table and TEST                                                                                                                                  | 30 min        | Sep 29                 | C         |
| 17      | Reason For Solution                          | Write Reasons for solutions                                                                                                                                      | 20 min        | Oct 2                  | A         |
| 18      | Rationale                                    | Reason for using Python                                                                                                                                          | 30 min        | Oct 3                  | A         |
| 19      | Sources                                      | Add cited sources                                                                                                                                                | 20 min        | Oct 4                  | A. C      |


## Test plan
| Test No | Type of test      | Area Tested                   | Procedure                                                                                                                                             | Test Outcome                                                           | Time estimate | Target completion date | Criterion |
|---------|-------------------|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------|---------------|------------------------|-----------|
| 1       | Unit Testing      | Login System                  | 1.Enter username and password 2. If correct enters wallet, if not enter username and password again 2 more chances given                              | Confirm the user can login and have three attempts to login correctly  | 15 min        | Sep 30                 | B         |
| 2       | Unit Testing      | Withdraw and Deposit Function | 1. User picks one or two (Withdrawal or Deposit) 2. Amount to withdraw/deposit 3.Reason for withdraw/deposit 4. Display that it worked through succes | Confirm the user can deposit/withdraw Ethereum through the wallet      | 10 min        | Sep 30                 | B         |
| 3       | Unit Testing      | Balance Function              | 1. User picks three to check balance 2. Program adds sum of transcation 3. Prints sum                                                                 | Confirm that the balance is correctly displayed                        | 7 min         | Sep 30                 | B         |
| 4       | Unit Testing      | Current Rate of ETH           | 1. Request html code for website 2.Parse specfic element in html code 3. Print current rate of ETH                                                    | Confirm that the Rate updates and displays the newest rate             | 20 min        | Sep 30                 | B         |
| 5       | Usability Testing | User ability                  | 1. Easy display of options for user to pick from 2. User picks option 3.Runs task 4. Continues back to options unless clicks exit number(6)           | Confirm that the system works as a whole                               | 5min          | Sep 30                 | B         |

# Criteria C: Development

## Tools / Techniques used
1. Functions
2. For/while loops
3. Input Validation
4. If statements
5. Web Scraping

## Login System

```.py
def login(name:str, password:str)->bool:
    with open('user.csv',mode='r') as f:
        data = f.readlines()

    success = False
    for line in data:
        uname = line.split(',')[0]
        upass = line.split(',')[1].strip()#removes \n
        if uname == name and upass == password:
            success = True
            break
    return success


###
attemps = 3
in_name = input("Enter your username")
in_pass = input("Enter your password")
res = login(name=in_name, password=in_pass)
while res == False and attemps > 1:
    in_name = input("[ERROR WRONG USER] Enter your username")
    in_pass = input("Enter your password")
    res = login(name=in_name, password=in_pass)
    attemps -= 1
if res == False:
    print("sayonara")
    exit(1)#1 is code for exit without error
```
My client required a system to protect their private data. So, I have made a login system that allows the user to log in with an already existing Username and Password. The username and password are then checked with a CSV file that stores all user information. If it's the user's wallet, the Ethereum wallet will open; however, if it is not the user or the user enters the password wrong, it will give the person entering the username and password three chances to enter the correct username and password. The wallet will close if the user doesn’t enter the correct password and username three times.

## Menu System

```.py
while True:
    print("\nEthereum Wallet Menu:")
    print("1. Deposit")
    print("2. Withdraw")
    print("3. Check Balance")
    print("4. Check current rate")
    print("5. Description of Ethereum")
    print("6. Quit")


    choice = input("Enter your choice (1/2/3/4/5): ")
    if choice == "1":
        amount = float(input("Enter the amount to deposit: "))
    elif choice == "2":
        amount = float(input("Enter the amount to withdraw: "))
    elif choice == "3":
        print('Balance"')
    elif choice == "4":
        print('Getting the data from the web"')
    elif choice == "5":
        print('Getting the data from the web"')
    elif choice == "6":
        print("Exiting the Ethereum wallet.")
        break
    else:
        print("Invalid choice. Please select a valid option.")
```

This code allows the user to pick what they want to do in the Ethereum wallet. A while loop keeps repeating the options so the user can do multiple transactions without exiting the wallet. If loops allow the user to pick a specific number to get to a certain step, such as withdrawing, describing the coin, or exiting the wallet. 

## Deposit, Withdraw, and Balance

```.py
import datetime
while True:
    print("\nEthereum Wallet Menu:")
    print("1. Deposit")
    print("2. Withdraw")
    print("3. Check Balance")



    choice = input("Enter your choice (1/2/3): ")
    if choice == "1":
        amount = float(input("Enter the amount to deposit (ETH)  : "))
        while amount < 0:
            print("enter again")
            amount =float(input("Enter the amount to deposit (ETH)  : "))

        date = datetime.date.today()  # todays date
        category = input("Reason for deposit: ")
        line = f"{date},{amount},{category}\n"
        with open('Transactions.csv', mode='a') as f:
            f.writelines(line)
        print("Saved")
    if choice == "2":
        amount = (float(input("Enter the amount to withdraw (ETH)  : ")))

        while amount < 0:
            print("enter again [INVALID NUMBER}")
            amount = float(input("Enter the amount to deposit (ETH)  : "))


        date = datetime.date.today()  # todays date
        category = input("Reason for withdraw: ")
        line = f"{date},{-amount},{category}\n"
        with open('Transactions.csv', mode='a') as f:
            f.writelines(line)
        print("Funds Withdrawn")


    elif choice == "3":
        with open('Transactions.csv', mode='r') as f:
            data = f.readlines()
        balance = 0
        for line in data:
            
            date, amount, reason = line.strip().split(',')
            balance += float(amount)
        msg = f'Your Balance {date} is {balance}'
        print(msg)
    else:
        print("Invalid choice. Please select a valid option.")
```
This code allows the user to deposit, withdraw, and check the balance of their Ethereum wallet. It uses a little menu system that utilizes a while loop and three if statements to have the user pick which interaction they like. The deposit function allows the user to input the amount of Ether to the sixth decimal place, and if the user enters a negative number, it will ask to enter an accepted value. Once the user enters the amount they would like to deposit, the user can input the reason for the deposit, and it will be saved to the Transactions.csv file with the date, amount, and reason. The withdraw function works along the same lines, allowing the user to withdraw Ether and allocate a reason for the transaction but instead saves with a negative value for the amount withdrawn into the Transactions.csv file. The balance system works by reading each line of the Transaction.csv file and stripping the date and the reason. Then, it calculates the sum of all deposits and withdrawals and prints the sum with the date.

## Current Rate of Ether from the internet

```.py
from bs4 import BeautifulSoup
import requests
url = 'https://coinmarketcap.com/currencies/ethereum/'
page = requests.get(url)
soup = BeautifulSoup(page.text, 'html5lib')
output = soup.find('span', class_ = "sc-16891c57-0 dxubiK base-text")
print(f"This is the current rate of Ethureum {output.text} USD  ")
```
This code scrapes real-time data from the CoinMarketCap website [8]. It uses the BeutifulSoup library to parse the HTML code from the website. The code then uses the specific HTML element to take the current price of Ethereum and print it in the electronic ledger.

## Bar Graph of Deposit/Withdraws

```.py
 with open('Transactions.csv', mode='r') as f:
 data = f.readlines()
 deposits = 0
 withdrawals = 0
 for line in data:
 date, amount, reason = line.strip().split(",")
 if int(amount) > 0:
 deposits += int(amount)
 else:
 withdrawals += -1*int(amount)
 # create a simple graph
 deposits = deposits // 100
 withdrawals = withdrawals // 100
 bar_deposits = "deposits".ljust(20)
 bar_withdrawals = "withdrawals".ljust(20)
 for x in range(deposits):
 bar_deposits += "▥"
 for x in range(withdrawals):
 bar_withdrawals += "▥"
 print(f"{bar_deposits} {deposits}")
 print(f"{bar_withdrawals} {withdrawals}")
```
This code graphs the amount of Transactions and Withdraws. It uses the CSV file and accumulates the total amount of withdraws and deposits. Each deposit and withdrawal amount is divided by 100 for scaling purposes. The code then creates two bar strings deposits and withdraws. Finally, it graphs deposits and amounts along with there total amount.

## Video Proof



## Sources Cited
1. What is python used for? A beginner’s guide. Coursera. (n.d.). https://www.coursera.org/articles/what-is-python-used-for-a-beginners-guide-to-using-python 
2. Ahmed, M. (n.d.). Why is python so easy to learn?. LinkedIn. https://www.linkedin.com/pulse/why-python-so-easy-learn-maqsood-ahmed 
3. GoPract.com. (n.d.). The importance of libraries in Python, Data Science, and the applications they facilitate. GoPract. https://gopract.com/Pages/Importance-of-Libraries-Python-data-science-Applications-They-Facilitate.aspx#:~:text=Python%20libraries%20are%20pre%2Dwritten,data%20analysis%20and%20machine%20learning. 
4. Worsley, S. (2022, March 7). What is python? - the most versatile programming language. DataCamp. https://www.datacamp.com/blog/all-about-python-the-most-versatile-programming-language 
5. Tele, C. (n.d.). What is ethereum and how does it work?. Cointelegraph. https://cointelegraph.com/learn/what-is-ethereum-a-beginners-guide-to-eth-cryptocurrency 
6. Hayes, A. (n.d.). Blockchain facts: What is it, how it works, and how it can be used. Investopedia. https://www.investopedia.com/terms/b/blockchain.asp 
7. Golubev, S. (n.d.). The expansion of Decentralized Finance (DEFI) on the Ethereum Network. LinkedIn. https://www.linkedin.com/pulse/expansion-decentralized-finance-defi-ethereum-network-sergey-golubev 
8. CoinMarketCAP. (n.d.). Ethereum Price Today, ETH to USD live price, marketcap and Chart. CoinMarketCap. https://coinmarketcap.com/currencies/ethereum/ 



