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


## Proposed Solution

Design statement:
I will to design and make a Ethruuen Wallet for a client who is trying to set up an acounnt. The wallet will hold currency and is constructed using the software pyhton. It will take  30 days to make and will be evaluated according to the criteria (please check succes critera 1-6).

** Ethereum (ETH) is a decentralized blockchain network powered by the Ether token. It enables users to transact, earn interest on their holdings through staking, use and store nonfungible tokens (NFTs), and trade cryptocurrencies. [1] Ethereum is a global platform that uses a digital ledger through multiple computers to maintain a secure and decentralized record of transactions.[2] The growth of Ethereum is expected to continue due to its widespread adoption as a platform with ongoing technological advancements, increased institutional interest, and a growing ecosystem of innovative projects; Ethereum's value is likely to rise because of its central role in the evolving landscape of decentralized finance and digital assets.[3] **

Justify the tools/structure of your solution

## Success Criteria
1. The electronic ledger is a text-based software (Runs in the Terminal).
2. The electronic ledger display the basic description of the cyrptocurrency selected.
3. The electronic ledger allows to enter, withdraw and record transactions.
4. The elctronic ledger displays current rate of coin
5. Login and Logout of Account
6. Converts rate of coin into differant country rate USD CAN JPN

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

## Record of Tasks
| Task No | Planned Action        | Planned Outcome                                                                          | Time estimate | Target completion date | Criterion |
|---------|-----------------------|------------------------------------------------------------------------------------------|---------------|------------------------|-----------|
| 1       | Create system diagram | To have a clear idea of the hardware and software requirements for the proposed solution | 10 min        | Sep 24                 | B         |
| 2       | Create a Login System | To have a way for the user to login to account and logout of account.                    | 30 min        | Sep 14                 | B,C       |
| 3       | Check With Client     | Client either approves 6 proposed ideas or denies them.                                  | 15 min        | Sep 18                 | A         |

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



    choice = input("Enter your choice (1/2/3/4/5): ")
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
        amount = (float(input("Enter the amount to withdraw (USD)  : ")))

        while amount < 0:
            print("enter again [INVALID NUMBER}")
            amount = float(input("Enter the amount to deposit (USD)  : "))


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
