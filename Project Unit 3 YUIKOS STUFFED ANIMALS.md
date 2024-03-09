
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


# Criteria B-Solution Overview
### Diagrams
#### System Diagram

<img width="739" alt="Screenshot 2024-03-09 at 7 30 41 PM" src="https://github.com/K-Schriber/Unit-3-Comp-Sci/assets/142757998/f1ae2cb9-163c-4b89-b5ca-375b711d3ed6">

The system diagram of the Yuikos Stuffed Animal Incorporated application displays the input and output components of the system, along with the various systems used for the project. The input component is the keyboard used to input data into the application. The output components include the computer screen, which displays the application interface and the various systems used for the project. These systems include the programming languages used (Python and KivyMD), the computer details (Processor, version, memory, etc.), the module, and the database. The module refers to the DatabaseWorker class used to interact with the SQLite database, while the database stores all the information related to the application.
#### Wireframe Diagram



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
