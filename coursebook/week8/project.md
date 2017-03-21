# Create an OAuth2 service

## Create a application

`This application` will:

- store sensitive information securely
    - hash passwords with [bcrypt](https://github.com/kelektiv/node.bcrypt.js/) (fyi: [wiki](https://en.wikipedia.org/wiki/Bcrypt))
- use validation
- use sessions
- host an OAuth2 service for third-party applications

### User Stories

#### Sign up
As a user, I can:
- sign up with an email, username, and password
- **not** sign up with an email that is already in use
- **not** sign up with a password that is already in use
- **not** sign up with a weak password

#### Log in
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
- add a third-party application, which will:
    - generate a `client_id`
    - generate a `client_secret`

As a third-party application, I can:
- allow my users to authenticate with `this application` using OAuth2 flow
- make authenticated requests on behalf of my users, using an `access_token`
    - eg. display profile information from `this application`
