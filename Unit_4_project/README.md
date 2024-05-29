# Criteria C : Documenting the development

## List of techniques used
- Flask Library/Routes
- HTTP - GET and POST requests
- Python/Django inside HTML
- CSS Styling
- SQLITE Databases
- If statements
- Variables
- Functions
- Lists
- Token-based authentication eerrmmm

# Memes database
The memes.database which is ran through the driver SQLlite stores all the information from memes to users information. To access/query/add/delete data I first need to connect to my program (python.file) with the database. The function `get_db` below connects to the database [^1] . It ensures that a single connection is used per request to avoid opening multiple connections to the database. 
```.py
def get_db():
    db = getattr(g, '_database', None) #defines the db as database, also utalizes an object provided by flask called g to store data during lifetime of request [^1]
    if db is None: #checks if there isn't a current database connection for request 
        db = g._database = sqlite3.connect(DATABASE)
        db.row_factory = sqlite3.Row
    return db
```
The next function I use disconnects from the database, ensuring that the connection is closed after each request is processed. [^1].

```.py

def close_connection(exception):
    db = getattr(g, '_database', None)
    if db is not None: # Checks if there is an existing database connection and if there is disconnected from Database
        db.close()
```
The pros of using a function is whenever you need to Query the data base you aren't repetetive with the connection and closing connection code. This also allows me to focus on the more complex and important aspects of the application, such as the user interface and functionality.

# CSS Styling
CSS (Cascade Style Sheet) styling allows you to have a standard format and presentation for the spacing of images/textboxs/headers/etc. In this project I utalized a premade template [^2]. 

```.css
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

header {
    background-color: #333;
    color: #fff;
    padding: 1em;
    text-align: center;
}

nav a {
    color: #fff;
    margin: 0 1em;
    text-decoration: none;
}

main {
    padding: 2em;
}

h2 {
    color: #333;
}

form label {
    display: block;
    margin-top: 1em;
}

form input[type="text"],
form input[type="password"] {
    width: 100%;
    padding: 0.5em;
    margin-top: 0.5em;
}

form input[type="submit"] {
    margin-top: 1em;
    padding: 0.5em 2em;
    background-color: #333;
    color: #fff;
    border: none;
    cursor: pointer;
}

ul {
    list-style-type: none;
    padding: 0;
}

ul li {
    margin: 1em 0;
}

ul li img {
    max-width: 100%;
    height: auto;
    grid-column: 1;
  grid-row: 2 / 5;}
```

# Base HTML
To maintain the same visual format within each page of the program the use of a html named base. This HTML file is the shell which all the other pages will be rendered from [^3]. In other words, it provides the same format for the header, depending if you're logged in the header will show login /register or Home/Add Meme/Logout/Profile.

Fig 1: LOGGED IN

<img width="432" alt="Screenshot 2024-05-25 at 8 09 26 PM" src="https://github.com/K-Schriber/Unit-4-Comp-Sci/assets/142757998/51d5dc01-78b5-4470-af81-2a3bd46cd2ad">


Fig 2: LOGGED OUT

<img width="539" alt="Screenshot 2024-05-25 at 8 09 19 PM" src="https://github.com/K-Schriber/Unit-4-Comp-Sci/assets/142757998/d90cfff6-689e-49da-9d28-1d9290c163cf">


```html
<!DOCTYPE html>
<html>
<head>
    <title>Flask Meme Manager</title>
    <link rel="stylesheet" type="text/css" href="{{ url_for('static', filename='style.css') }}">
</head>
<body>
    <header>
        <h1>Meme Manager</h1>
        {% if session.user_id %}
        <nav>
            <a href="{{ url_for('home') }}">Home</a>
            <a href="{{ url_for('manage_memes') }}">Add Meme</a>
            <a href="{{ url_for('logout') }}">Logout</a>
            <a href="{{ url_for('profile') }}">Profile</a>
        </nav>

        {% else %}
        <nav>
            <a href="{{ url_for('login') }}">Login</a>
            <a href="{{ url_for('register') }}">Register</a>
        </nav>
        {% endif %}
    </header>
    <main>
        {% block content %}{% endblock %}
    </main>
</body>
</html>
```

## Session function
The session function stores information about a user's session across multiple requests. In the Flask application, cookies and sessions are closely related that the session data in this case `user_id` is stored in cookies. When you store information in the session object in Flask the data is serialized and placed into a cookie that is sent to the user's browser (Figure 3)[^6]. This session cookie is then included in all the next HTTP requests. By verifying the session cookie Flask can retrieve the stored session data. This ensures a secure and consistent user experience throughout the application [^6]. 

The function 
```.py
@app.route('/')
def index():
    if not session.get('user_id'): # if the session is not user id then redirects for login
        return redirect(url_for('login'))
    return redirect(url_for('home')) #else it stays on home page
```

Figure 3: User Cookie: User_id Cookie = 1

<img width="451" alt="Screenshot 2024-05-27 at 8 39 02 AM" src="https://github.com/K-Schriber/Unit-4-Comp-Sci/assets/142757998/f4b3a37a-1594-4310-92e3-e53a28560b43">


# Succes Criteria 1: The application for the Meme Reddit has a login/register system
I have created a login/registration system that allows users to each have there own account by loggin in or registering if they don't have an account. 


## Registration
The first part of the process of the application is registering. To create the webserver page the url endpoint is called `/register`.  The following `registration` function allows new users to create an account by providing a username and password. When the user clicks submit it stores the user's entered information. This process of appending data to the database is a Post request in which data is saved to the server in this case the SQLLITE database. The program uses a try block to test if there are any errors in the entries and uses a except block to handle the error by returning the `sqlite3.IntegrityError`. The error is if the user already exists [^4]. The SQL query uses ? which is place holder for the values doing this changes the query into a parameterized query [^5]. In this type of query actual values are provided separately from the SQL statement itself this is done to prevent SQL Injections which is a web attack that uses malicious SQL code for backend database manipulation to access information that not intended to be displayed [^5]. Before the username and password are appended to the database the password is hashed for extra security. Hashing involves taking an input `password` and converting it into a fixed-size string of characters using a mathematical function. Figure 4: Registration page

The code for the registration system is below. I have provided comments next to the code to provide better understanding

```.py
@app.route('/register', methods=['GET', 'POST']) # defines the URL end point and the HTTP methods GET and POST
def register():
    error = None
    if request.method == ['POST']: 
        username = request.form['username'] # User inputs username into text box
        password = request.form['password'] # User inputs password into text box
    db = get_db() #connection to database
    try: # Runs the block of code within and checks to see if there is a repeated user if there is it goes to except block
        db.execute('INSERT INTO user (username, password) VALUES (?, ?)', # ? place holder values 
                   (username, generate_password_hash(password))) # Inserts the two values of username/ passowrd into placeholder values database hashing password
        db.commit()
        return redirect(url_for('login')) # Redirects user to Url route /Login
    except sqlite3.IntegrityError: # Brings up error and returns prompt to user
        error = 'Username already taken. Please choose another.'
    return render_template('register.html', error=error) # If errors returns to register template 

```
Figure 4: REGISTRATION PAGE

<img width="1511" alt="Screenshot 2024-05-27 at 9 10 54 AM" src="https://github.com/K-Schriber/Unit-4-Comp-Sci/assets/142757998/39ec58c0-f0d0-4c51-832a-47b96d029751">

## Login 
The login system works similary to the registration system except will only allow the user to login if there is an exsisting account. The login page asks the user to input username and password into two text boxes and has a submit button. Once the user clicks the submit button using an if statement if it sends a POST request. Then the username/password are saved in two variables and the the program connects to the database. The database then does a parameteraidsed query (Query for SQL injection prevention) to see if the username is located in the database. If it is then it checks if the provided password matches the hashed password stored in the database. If both match username/password match in database the users id is put into a session via `user_id` and the fucntion redirects the user to the home page. Else if they don't match the user is returned with an error. The HTML rendering of the login figure 5

Figure 5: LOGIN PAGE

<img width="1501" alt="Screenshot 2024-05-27 at 9 08 58 AM" src="https://github.com/K-Schriber/Unit-4-Comp-Sci/assets/142757998/f728564c-bf85-4fa4-80ab-8f7c8a5530f8">

Code for login page 
```.py
@app.route('/login', methods=['GET', 'POST'])
def login():
    error = None
    if request.method == 'POST':
        username = request.form['username']
        password = request.form['password']
        db = get_db()
        cur = db.execute('SELECT * FROM user WHERE username = ?', (username,))
        user = cur.fetchone()
        if user and check_password_hash(user['password'], password):
            session['user_id'] = user['id']
            return redirect(url_for('home'))
        else:
            error = 'Invalid Credentials. Please try again.'
    return render_template('login.html', error=error)
```

# Succes Criteria 2: A posting system to EDIT/CREATE/DELETE comments
The user is able to edit, create, and review comments under memes. This allows multiple users to add input about the meme.

## Adding Comment
The first part of the comments system is letting users be able to add comments. To add comments it uses a function called Meme details. The first step is connection to the database. Then it uses a if Statement to check if the the user has clicked the comments button and if it's a `POST` request. If it is it the users comment is saved into a variable called content and then a insert paramatized query is execute for three values `content`, `meme_id`, and `user_id`. After the values are commited (saved) to the table Comment the data bases closes and the meme.html is rendered.  A time stamp is also saved into the comments table to show when users made comments. However if the HTTP request is a `GET` request then the function gets the meme details along with all the associated comments. This first query fetches the details of a specific meme,  category name, and the username of its creator. The result is stored in the meme variable. The next query gets all comments associated with the specified meme and the username of each commenter. The results are stored in the `comments` variable. The meme detail HTML is then Rendered Figure 6. More details about the SQL queries are next to the code below.

```.py
@app.route('/meme/<int:meme_id>', methods=['GET', 'POST'])
def meme_detail(meme_id):
    if not session.get('user_id'):
        return redirect(url_for('login')) #Extra Security to make sure the User is in the right session
    
    db = get_db()
    if request.method == 'POST':
        content = request.form['content']
        db.execute('INSERT INTO comment (content, meme_id, user_id) VALUES (?, ?, ?)',
                   (content, meme_id, session['user_id']))
        db.commit()
        return redirect(url_for('meme_detail', meme_id=meme_id))
    
    cur = db.execute('SELECT meme.*, category.name as category_name, user.username as creator_name ' # Selects all columns from the meme table and selects the name column from the category table and renames it to category_name
                     'FROM meme '
                     'JOIN category ON meme.category_id = category.id ' #joins  the meme and category tables and matches rows so meme.category_id equals category.id
                     'JOIN user ON meme.created_by = user.id ' # joins meme and user tables and matches rows so meme.created_id equals user_id
                     'WHERE meme.id = ?', (meme_id,))
    meme = cur.fetchone()
    
    cur = db.execute('SELECT comment.*, user.username as commenter_name ' # selects all collums from table users
                     'FROM comment ' 
                     'JOIN user ON comment.user_id = user.id ' # joins the comment and user table matching rows  so comment.user_id = user.id
                     'WHERE comment.meme_id = ?', (meme_id,)) #filters the results so it only includes rows that match the meme_id
    comments = cur.fetchall()
    return render_template('meme_detail.html', meme=meme, comments=comments)
```


Figure 6: Add Comment System : The Comments display the user who created it and the time it was added. It also shows other users comments on the post

<img width="483" alt="Screenshot 2024-05-29 at 9 32 13 AM" src="https://github.com/K-Schriber/Unit-4-Comp-Sci/assets/142757998/e635ec8c-c307-4221-8465-5767b988f6df">


### Citations

[^1]:USING SQLITE WITH FLASK, Pallets, msiz07-flask-docs-ja.readthedocs.io/ja/latest/patterns/sqlite3.html. 
[^2]:“Styles & CSS.” Docs, docs.astro.build/en/guides/styling/. Accessed 26 May 2024. 
[^3]:“Template Extending.” Template Extending · HonKit, tutorial.djangogirls.org/en/template_extending/. Accessed 26 May 2024. 
[^4]: “Try, except, Else, Finally in Python (Exception Handling).” Nkmk Note, note.nkmk.me/en/python-try-except-else-finally/. Accessed 26 May 2024. 
[^5]:“Protecting Databases with Parameterized Queries.” Blue Goat Cyber, 21 Apr. 2024, bluegoatcyber.com/blog/protecting-databases-with-parameterized-queries/. 
[^6]:Ruscica, Tim. “Sessions.” Flask Tutorial, www.techwithtim.net/tutorials/flask/sessions. Accessed 26 May 2024. 
[^7]:
[^8]:
