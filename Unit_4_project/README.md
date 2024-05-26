# Criteria C : Documenting the development

## List of techniques used
- Flask Library/Routes
- Python/Javascript inside HTML
- CSS Styling
- Object-Oriented Programming(OOP) / SQLITE Databases
- If statements
- Variables
- Functions
- Lists
- Token-based authentication

# Memes database
The memes.database which is ran through the driver SQLlite stores all the information from memes to users information. To access/query/add/delete data I first need to connect to my program (python.file) with the database. The function [get_db] below connects to the database [^1] . It ensures that a single connection is used per request to avoid opening multiple connections to the database. 
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
CSS styling allows you to have a standard format and presentation for the spacing of images/textboxs/headers/etc. In this project I utalized a premade template [^2]. The CSS visual appearance is below.

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





## Succes Criteria 1: The application for the Meme Reddit has a login/register system
I have created a login/registration system that allows users to each have there own account by loggin in or registering if they don't have an account. The first part of the registration system is the [[register page]]  


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
### Citations
[^1]:USING SQLITE WITH FLASK, Pallets, msiz07-flask-docs-ja.readthedocs.io/ja/latest/patterns/sqlite3.html. 
[^2]
[^3]
