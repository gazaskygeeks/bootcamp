# Create an OAuth2 service

## Create a application

`This application` will:

- Store sensitive information securely
- Use validation
- Use sessions
- Host an OAuth2 service for third-party applications


### User Stories

#### Sign up
As a user, I can:
- sign up with an email, username, and password
- **not** sign up with an email that is already in use
- **not** sign up with a password that is already in use
- **not** sign up with a weak password

#### Login
As a user, I can:
- log in using email/username, and password
- return to the site without needing to sign in again, using sessions/cookies

#### Log out:
As a user, I can:
- log out of the app, and if I return, I must log in again

#### View Profile
As a user, I can:
- view all my user information, but not my password

#### Edit Profile
As a user, I can:
- change my email, username, and password
- add a personal bio
- change my personal bio

#### OAuth service
As a user, I can:
- Add a third-party application, which will:
    - Generate a client_id
    - Generate a client_secret

As a third-party application, I can:
- allow my users to authenticate using OAuth2 flow
- redirect my users to an endpoint, with my { client_id, client_secret }
    - this page will allow my users to enter their user/password for this app
- request an access_token via my users
- make authenticated requests on behalf of my users, using an access_token
