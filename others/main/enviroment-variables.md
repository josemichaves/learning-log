# Enviroment Variables

An environment variable is a variable whose value is set outside the program, typically through functionality built into the operating system or microservice.

```text
MY_PASSWORD = '123456789'
```

All the names of the env variables are in uppercase by convention

Normally this env variables lives inside a file called _.env_ and **it never should be pushed in a version control manager**, because contains sensible information, such as ports, ip address, passwords, secrets, etc.

It's used to store data that only needs to live in our computer, and it should not be shared with anyone more.

We can access this env variables in all the project by calling it with `process.env.nameOfTheVariable`:

```javascript
MY_SECRET = 'FDSKJA122NKLSDV'

--------------------------------------

const makeMySecretPublic = () => {
    secret = process.env.MY_SECRET
    console.log(secret)
}

makeMySecretPublic()
/// 'FDSKJA122NKLSDV'
```



