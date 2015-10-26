# Database userdb

Status: active

Contact/Maintainer: the LMFDB website relies on it,
somehow it maintains itself.

Description: holds the data of all users to log in and the tokens
are there to give out new accounts.

Todo:
* ...


## Collection tokens

tokens for new users, entries should expire and be cleaned up

* Field 1: ...
* Field 2: ...

## Collection users

used here:

https://github.com/LMFDB/lmfdb/tree/master/lmfdb/users

and based on flask's user plugin

* _id: the unique username
* email: registered email address
* full_name: self explanatory
* password: hashed with a salt and iterations
* url: the homepage of the user
* about: some personal description
* created: timestamp when created

