# Criteria C : Documenting the development

## List of techniques used
- Flask Library/Routes
- Python/Javascript inside HTML
- CSS Styling
- Object-Oriented Programming(OOP)
- For loops
- If statements
- Variables
- Functions
- Lists
- Token-based authentication

# CSS Styling
CSS styling allows you to have a standard format and presentation for the spacing of images/textboxs/headers/etc. In this project I utalized a premade template [^1]. The CSS visual appearance is below.

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
To maintain the same visual format within each page of the program the use of a html named base. This HTML file is the shell which all the other pages will be rendered from [^2]. In other words, it provides the same format for the header, depending if you're logged in the header will show login /register or Home/Add Meme/Logout/Profile.

Fig 1: LOGGED IN
<img width="1147" alt="Screenshot 2024-05-24 at 11 03 48 AM" src="https://github.com/K-Schriber/Unit-4-Comp-Sci/assets/142757998/0f95bc84-7c5c-4c54-9648-9961a6e552f5">

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
Since my users needs an application to manange multiple users . I have created a login system that 


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
[^1]:

