# WR3 Fake Reddit Review
</hr>

### MVP
- users can create account
- users can login
- users can view posts
- users can add post
- users can edit posts
- users can vier their profile to see their post and karma
</br>
</br>
***icebox***
- users can comment on post
- users can can upvote/downvote posts

#### Database
- Schemas:

users
``` SQL
CREATE TABLE users(
    user_id SERIAL PRIMARY KEY,
    first_name TEXT,
    last_name TEXT,
    email VARCHAR(60),
    password TEXT,
    karma_score INT
)
```
posts
```SQL
CREATE TABLE posts(
post_id SERIAL PRIMARY KEY,
body TEXT,
img TEXT,
post_karma_score INT,
user_id INT REFERENCES users(user_id)
)
```
comments
```SQL
CREATE TABLE comments(
    comment_id SERIAL PRIMARY KEY,
    body TEXT,
    comment_karma_score TEXT,
    post_id INT REFERENCES post(post_id),
    user_id INT REFERENCES users(user_id)
)
```

#### Server
- Dependencies:
    - express
    - massive
    - bcrypt
    - dotenv
    - express-session
- File structure:
    - server/
        - index.js
        - ctrl/
            - authCtrl.js
            - postCtrl.js


#### Front-End
- Dependencies
    - axios
    - redux
    - react-redux
    - redux-promise-middleware
    - react-router-dom
- File structure
    - src/
    - App.js
    - App.css
    - Reset.css
    - redex/
        - store.js
        - reducer.js
    - components/
        - Header
        - Login
        - FrontPage
        - 