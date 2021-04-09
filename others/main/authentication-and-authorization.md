# Authentication and Authorization

When we're creating an authentication and authorization system we have two part that we need to configure, the server side and the client side.

## Client Side

In the client side we'll do basic checks such as if the client is logged now, if the two password are the same \(while register\) or if the email is a correct email, but never we'll make and important check in the client side, as the web is very insecure and the data can be altered easily.

Once we've created an account and we logged successfully we should create a "context" that persists across all the web page to tell the application that we're logged and show things that otherwise we're not able to see it \(pages only for registered users\) and we also use this context to know that we have user and what user is it, so we can do certain actions based in the user type.

We'll also be saving a user token signed by us to know if this user is correct.

## Server Side

In the other part we have the backend or the server side, in this are is where all the security will live, here we should do all the checks necessary to ensure a secure authentication system.

First of all if the data has passed the checks in the client side, we'll receive this data and we else need to do the same checks in the server, as the data can be altered in the client-side, once we've done this tests we can store the data and create an user

When we create a user the most important thing is to store the data safely so we need to make an important thing, encrypt all the sensible information, mainly the password, we cannot store the password of an user in plain text as any user that could enter in our database could easily see this password, so we need to encrypt this data.

Once we encrypt the data we'll expend a token signed by us \(JWT for example\) and this token will ensure that this user is created by us and not altered we need to check if the token is correct every time the user logs in.

## Libraries to use

* [Json Web Token](https://jwt.io/): This library will help us to create tokens signed by us \(we sign a token by our secret that is in the environment variable\).
* [bcrypt](https://www.npmjs.com/package/bcrypt): This library its useful to encrypt password and compare encrypted passwords and plain text passwords.
* [Formik](https://formik.org/): This is a library for react that help us with the forms, but we can also do simple checks in it such as if an email is valid, a password has certain amount of characters, etc.



