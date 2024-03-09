
<img width="1275" alt="Screenshot 2024-03-05 at 3 41 49 PM" src="https://github.com/K-Schriber/Unit-3-Comp-Sci/assets/142757998/ac1e8cfc-eb83-4ac6-9d00-c7292dc09d71"> Image by Dalle- E


# Criteria A-Planning 
### Definition of the Problem

Yuikos Stuffed Animal Incorporated has been selling stuffed animals for six months. Yuiko’s stuffed animals are family-friendly toys that bring happiness to the whole family. Over the past few weeks Yuiko has reportedly been offered many lucrative deals to sell her company, but opted instead to continue the business on her own. As the business has grown, Yuiko herself has found it difficult to manage orders. And is in urgent need of an application to manage raw materials, track transactions, and create stuffed animals if sufficient resources are there. Yuiko wants the application to be password-protected and encrypted so no trade secrets are leaked. Yuiko has also demanded that the application graph the influx of raw resources in and out of the company.



### Success criteria
1.The application has a feature to track balance and purchases.

2.The application offers a login feature that is password and username-protected, along with encryption for extra security.

3.The application allows users to purchase raw materials if there are insufficient materials.

4.The application tracks the resources bought and used and creates a line graph to track the influx.

5.The application allows new users to create an account



### Design statement
I will design an aplication for Yuiko Inc, a stuffed animal buisness. This application will serve to display/manage the buisness finacial and orders. It will be a computer application, and will be developed in the one month period.

---

### Rationale for proposed solution
For this project, I will use the Python programming language, KivyMD library for the graphic user interface, and SQL lite for databases to store the information.


Based on the client’s request, I will be working on designing and developing an application can easily mangage Yuikos Stuffed Animals incorporate. The application will run on the programing language Python, KivyMD library for the user interface, and SQL Lite for the databases of the application.

#### Why Python?
Python has over 8.2 million Python developers[^1]. Meaning Python is an active community that offers a lof of support for projects. Python is an effective choice for many kinds of development projects[^2]. A wide range of resources and libraries to create the perfect program. Python has a simple syntax that allows users to understand and develop code more easily[^3].

#### Why KivyMD?
Kivy MD offers users access to an extensive collection of Material design compliant widgets[^4], such as sliders, buttons, chat boxes, and more. These features allow Yuiko and Co a simple GUI that’s easy to follow. Along with being multitouch application software, KivyMD can be run on multiple platforms such as Android, IOS, Linux, and Windows. This is perfect for Yuiko and CO so staff can access the program from many devices.[^5] Another advantage of using Kivy is it’s completely free, so there is no paying for software. Kivy connects with Python, which is rich in libraries that ease the development process of applications.[^6] With Python having a lot of online support, you can run an application in no time. 


#### Why SQLite?
SQLite is very flexible, allowing you to work/access multiple databases in one session[^7]. SQLite is also serverless (it doesn’t require a server to request data from) and can run on any operating system. This makes it easy for Yuiko to request data about orders and inventory. SQLite works well as a database engine for sites with medium traffic, up to 100k daily visits[^8]. This is perfect for Yuiko and CO cause as the business grows, she can start adding an online shop.

### Citations
[^1]:“Why Is Python so Popular?” Pulumi, PULMI, www.pulumi.com/why-is-python-so-popular/. Accessed 25 Feb. 2024. 

[^2]:"Why Choose Python." Python.org, Python SoftwareFoundation. https://www.python.org/about/gettingstarted, Accessed 25 Feb. 2023 

[^3]:Nyakundi, Hillary. “Why Python Is Good for Beginners – and How to Start Learning It.” freeCodeCamp.Org, 1 Mar. 2023, www.freecodecamp.org/news/why-learn-python-and-how-to-get-started/#:~:text=Compared%20to%20other%20languages%2C%20Python,a%20shorter%20period%20of%20time. Accessed 25 Feb. 2024. 



[^4]:“Kivy Basics¶.” Kivy, KIVY, kivy.org/doc/stable/guide/basic.html. Accessed 26 Feb. 2024. 
www.analyticsvidhya.com/blog/2021/06/creating-android-ml-app-kivymd/#:~:text=KivyMD%20is%20built%20on%20the. Accessed 13 Feb. 2023.


[^5]:“What Is Kivy?: Need and Importance: Advantages and Disadvantages.” EDUCBA, 3 Apr. 2023, www.educba.com/what-is-kivy/. Accessed 26 Feb. 2024. 

[^6]:Mieczkowski, Oskar. “Python for Mobile App Development in 2023 – Kivy vs. BeeWare.” AI, Monterail Sp. z o. o., 7 June 2023, www.monterail.com/blog/python-for-mobile-app-development. Accessed 26 Feb. 2024. 

[^7]:S, Ravikiran A. “What Is Sqlite? And When to Use It?” Simplilearn.Com, Simplilearn, 16 Feb. 2023, www.simplilearn.com/tutorials/sql-tutorial/what-is-sqlite#:~:text=SQLite%20facilitates%20you%20to%20work,needs%20no%20setup%20or%20administration. Accessed 26 Feb. 2024. 

[^8]:“Appropriate Uses For SQLite.” Appropriate Uses for SQLite, SQLITe, www.sqlite.org/whentouse.html. Accessed 26 Feb. 2024. 


# Criteria B-Solution Overview
### Diagrams
#### System Diagram

<img width="739" alt="Screenshot 2024-03-09 at 7 30 41 PM" src="https://github.com/K-Schriber/Unit-3-Comp-Sci/assets/142757998/f1ae2cb9-163c-4b89-b5ca-375b711d3ed6">

The system diagram of the Yuikos Stuffed Animal Incorporated application displays the input and output components of the system, along with the various systems used for the project. The input component is the keyboard used to input data into the application. The output components include the computer screen, which displays the application interface and the various systems used for the project. These systems include the programming languages used (Python and KivyMD), the computer details (Processor, version, memory, etc.), the module, and the database. The module refers to the DatabaseWorker class used to interact with the SQLite database, while the database stores all the information related to the application.
#### Wireframe Diagram




# Criteria C-Development
## Techniques Used
OOP paradigm
KivyMD Library
Relational databases
SQLite
functions
if statements
## Computational Thinking
####Python File Set up
‘’’.py
Import sqlite3
from kivy.uix.button import Button
from kivymd.app import MDApp
from kivy.core.window import Window
from kivymd.uix.datatables import MDDataTable
from kivymd.uix.dialog import MDDialog
from kivymd.uix.screen import MDScreen
from kivymd.uix.button import MDFlatButton
from kivy.uix.screenmanager import ScreenManager
from my_lib import DatabaseWorker
from my_lib import make_hash
import datetime
‘’’
This code imports the serval libraries needed for the Yuikos Application. The import of SQLite 3 allows us to interact with and change SQLite databases. The Kivymd imports all directly edit the GUI screen of the application, each import has a different function (button, slider, new screen, etc). The use of the library DateTime to track the time and day an order is placed. And the import of the class DatabaseWorker and  


## Proposed solution

### Criteria number 2: The application has a login feature and an account registration. Once the user enters their details, the data is saved to the database and encrypted.

![](https://github.com/AleksandarDzudzevic/Project_Unit_3/blob/main/login_screen_proof.gif)

Fig. 8 Represent Criteria 2, by showcasing a functional login. The first screen login shows consist of two text fields (1) username and (2) password. If the user and password match with one in the database the user is logged in. 
#### LoginScreen Python code




#### LoginScreen Python code
```.py
def try_change_to_third(self):
   password = self.ids.password.text
   username = self.ids.username.text
   user = db.search(f"SELECT * From Users WHERE name = '{username}' and password = '{password}'")
   if user:
       self.parent.current = 'Third'
   else:
       dialog = MDDialog(title='The Username or Password is Incorrect ')
       dialog.open()


```
Fig. 9 

Shows the Python code used for the Login system. Once the user clicks login after entering the user name and password, it runs through the try_change_to_third function. The user input is saved into two variables: username and password, respectively. The database (db) is then searched using an SQL query for the values that the user entered. If the values are located in the database, the system opens and moves to the main screen (third screen). If the username or password is incorrect and is not found in the database, a dialog box pops up, saying that the values entered are wrong. 



<FirstScreen>:


   MDLabel:
       text: "LOGIN"
       halign: "center"
       valign: "middle"
       font_size: "50sp"
       color: "darkblue"
       pos_hint: {"center_x": 0.5, "center_y": 0.85}
   MyButton:
       text: "Register"
       size_hint: 0.25, 0.2
       pos_hint: {"right": 0.98, "y": 0.02}
       radius:[15,15,15,15]
       on_release:
           root.try_change_to_second()


   MyButton:
       text: "Login"
       size_hint: 0.25, 0.2
       pos_hint: {"right": 0.2, "y": 0.02}
       radius:[15,15,15,15]
       on_release:
           root.try_change_to_third()










   TextInput:
       id: username
       hint_text: "Enter Username or Email"
       size_hint: 0.8, 0.1
       pos_hint: {"center_x": 0.5, "center_y": 0.6}
       font_size: "30sp"


   TextInput:
       id: password
       hint_text: "Enter Password"
       size_hint: 0.8, 0.1
       pos_hint: {"center_x": 0.5, "center_y": 0.4}
       font_size: "30sp"

   ```
Fig. 10 Shows the KivyMD code used for the login screen and its functions. The function to check the username/password is try_to_change_third after the button is released. The layout of the GUI is very friendly and offers simple clearly labeled buttons to move around the application.  

 
![](https://github.com/AleksandarDzudzevic/Project_Unit_3/blob/main/registerScreen_proof.gif)

 Fig.11 

shows Criteria 5, where new users can create an account. The screen has four text fields (1) username, (2) email, (3) password, and (4) confirm password. If any of the text fields are left blank, a popup will appear, telling the user that all fields need to be filled in. Additionally, if the user doesn’t add an ‘@’ to the email address, the system deems it fake and sends an invalid email address pop-up. If all the fields are entered but the password doesn’t match the rewrite password, then the system will prompt an error and not let the user continue. Also, if the user already exists, it will not work. Finally, If all is correct under the requirements listed above, the data of users will be added to the database, and the user will be logged in. 

#### SignupScreen Python code
```.py

class SecondScreen(MDScreen):
   def go_back_to_first(self):
       self.manager.current = 'First'


   def try_change_to_third(self):
       username = self.ids.nun.text
       email = self.ids.ne.text
       password = self.ids.np.text
       check_pass = self.ids.pas.text


       if not username or not email or not password or not check_pass:
           dialog = MDDialog(title='Error', text='All fields are required.')
           dialog.open()
           return


       if '@' not in email:
           dialog = MDDialog(title='Error', text='Invalid email address.')
           dialog.open()
           return


       if password == check_pass:
           user = db.search(f"SELECT * From Users WHERE name = '{username}' and password = '{password}'")
           if user:
               dialog = MDDialog(title='That User already exists')
               dialog.open()
           else:
               save_info = f"Insert into Users (name, email, password, encrypt) values ('{username}', '{email}', '{password}', '{make_hash(password)}')"
               db.run_query(save_info)
               self.manager.current = "Third"
       Else: 
           dialog = MDDialog(title='Error', text='Passwords do not match.')
           dialog.open()
   pass

```
Fig. 12 shows the Python code used for the application's signup/registration feature. I used if statements to check whether text fields were filled in correctly. First, the function def try_change_to_third saves the user's input into three variables: name: username, email, password, and check password. Then if the user's inputs are nonexistent, require an ‘@’, already exist in the database, or the password doesn’t match, the system blocks the user from creating an account. To check if the user already has an account in the database, I decided to use an SQL query that checks every user if the username and password credentials match. If they do, a prompt will return asking the user to pick a different password/username. If that user doesn’t exist, it will insert the values (name, email, password) into the database and then a fourth value of the hash signature for the name/password is added as well. 



#### SignupScreen KivyMD code
```.kv                
<SecondScreen>:


   MDLabel:
       text: "Register"
       halign: "center"
       valign: "middle"
       font_size: "50sp"
       color: "darkblue"
       pos_hint: {"center_x": 0.5, "center_y": 0.85}
   MyButton:
       text: "Cancel"
       size_hint: 0.25, 0.15
       pos_hint: {"right": 0.98, "y": 0.02}
       radius:[15,15,15,15]
       on_release: root.go_back_to_first()


   TextInput:
       id: nun
       hint_text: "Enter Username"
       size_hint: 0.8, 0.1
       pos_hint: {"center_x": 0.5, "center_y": 0.7}
       font_size: "30sp"




   TextInput:
       id: ne
       hint_text: "Enter Email"
       size_hint: 0.8, 0.1
       pos_hint: {"center_x": 0.5, "center_y": 0.55}
       font_size: "30sp"


   TextInput:
       id:np


       hint_text: "Enter Password"
       size_hint: 0.8, 0.1  # Adjust size_hint for the second TextInput
       pos_hint: {"center_x": 0.5, "center_y": 0.4}
       font_size: "30sp"
   TextInput:
       id: pas
       hint_text: "Confirm Password"
       size_hint: 0.8, 0.1
       pos_hint: {"center_x": 0.5, "center_y": 0.25}
       font_size: "30sp"


   MyButton:
       text: "Register"
       size_hint: 0.25, 0.2
       pos_hint: {"right": 0.2, "y": 0.02}
       radius:[15,15,15,15]
       on_release:


           root.try_change_to_third()

```
Fig.13 shows the KivyMD code used for the new user registration. It has four textboxes mentioned in Fig 11, a login button to run to check if the textbox entries are valued and a back button if the registration button was accidentally clicked. 



