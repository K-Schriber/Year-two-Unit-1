# Crypto Wallet


 ![ether-reach-the-ether](https://github.com/K-Schriber/Unit-1-Comp-Sci/assets/142757998/91d4c72d-feee-4aec-9861-aa653dfd6424)

<sub>Ethereum GIF by ethmemes</sub>

# Criteria A: Planning

## Problem definition

Ms. Sato is a local trader who is interested in the emerging market of cryptocurrencies. She has started to buy and sell electronic currencies, however at the moment she is tracking all his transaction using a ledger in a spreadsheet which is starting to become burdensome and too disorganized. It is also difficult for Ms Sato to find past transactions or important statistics about the currency. Ms Sato is in need of a digital ledger that helps her track the amount of the cryptocurrency, the transactions, along with useful statistics. Ms. Sato is interested in the cryptocurrency Ether and wishes to use it as her main cryptocurrency in the digital wallet. Ethereum (ETH) is a decentralized blockchain network powered by the Ether token. It enables users to transact, earn interest on their holdings through staking, use and store nonfungible tokens (NFTs), and trade cryptocurrencies. [1] Ethereum is a global platform that uses a digital ledger through multiple computers to maintain a secure and decentralized record of transactions.[2] The growth of Ethereum is expected to continue due to its widespread adoption as a platform with ongoing technological advancements, increased institutional interest, and a growing ecosystem of innovative projects; Ethereum's value is likely to rise because of its central role in the evolving landscape of decentralized finance and digital assets.[3]

Apart for this requirements, Ms Sato is open to explore a cryptocurrency selected by the developer.

An example of the data stored is 

| Date | Description | Category | Amount  |
|------|-------------|----------|---------|
| Sep 23 2022 | bought a house | Expenses | 10 BTC |
| Sep 24 2022 | food for house celebration | Food | 0.000001 BTC |


## Proposed Solution

Design statement:
I will to design and make a Ethruuen Wallet for a client who is trying to set up an acounnt. The wallet will hold currency and is constructed using the software pyhton. It will take  30 days to make and will be evaluated according to the criteria (please check succes critera 1-6).

** add a description of your coin and citation **

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

## 1 Login System
My client requires a system to protect their private data. I thought about using a login system to accomplish this requirement using a if condition and the open command to work with a csv file. More description of the code....
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
