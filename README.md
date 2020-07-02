# Flask RESTful API Example

## Prerequisite

Installed Python 3. Highly recommended to use `pyenv`, a wonderful tool for managing python version. For more detail: [https://github.com/pyenv/pyenv](https://github.com/pyenv/pyenv) 

## Python Virtual Environment

`virtualenv` is a python virtual environment where you can install packages and isolate them from all other Python packages. The basic commands:

- `$ pip install virtualenv` install using pip
- `$ virtualenv [directory name]` create virtual environment directory
- `$ source [directory name]/bin/activate` activate the virtual environment
- `$ deactivate` deactivate the virtual environment

## Install Required Packages

```bash
$ pip install -r requirements.txt
```

## Generate SQLite db file

Run python interpreter and execute the following python code:

```bash
$ python
>>> from api import db
>>> db.create_all()
```

## Run Application

```bash
$ python api.py
```

## APIs Call Example

```bash
$ curl -X  POST 'localhost:5000/users' \
-H 'x-access-token: [jwt token here]' \
-H 'Content-Type: application/json' \
-d '{"name":"arip", "password":"rahasia"}'
```

```bash
$ curl -X GET -u arip:rahasia 'localhost:5000/login'
```

```bash
$ curl -X GET 'localhost:5000/users'
```

```bash
$ curl -X GET 'localhost:5000/users/[public_id here]'
```

```bash
$ curl -X PUT 'localhost:5000/users/[public_id here]'
```

```bash
$ curl -X DELETE 'localhost:5000/users/[public_id here]'
```