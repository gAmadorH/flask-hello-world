# flask-hello-world

A simple Flask hello world application.

## Virtual environment

Create a project folder and create a virtual environment and activate.

```bash
mkdir flask-hello-world && cd $_
python -m venv .venv --python=python3.8
source .venv/bin/activate
```

## Install Flask

First create a file to save dependencies (only Flask dependency in this case).  
The must common name for this file is `requirements.txt`, so:

```bash
touch requirements.txt
```

Now you need to define your dependencies, and the file looks like this:

```txt
flask==1.1.2
```

You can check Flask releases in: [https://github.com/pallets/flask/releases](https://github.com/pallets/flask/releases)  
To install, you just to need run:

```bash
pip install -r requirements.txt
```

Now check installed dependencies (Flask and its dependencies).

```bash
pip freeze
```

## Create a Hello World app

Create a main file call `main.py`.

```bash
touch main.py
```

And then put the next code:

```python
from flask import Flask

app = Flask(__name__)


@app.route('/')
def hello():
  return 'Hello world with Flask'
```

## Run your new app

To run your app, first you need to set a environment variable called `FLASK_APP`  
and its value is the name of your file where is your app (`main.py` in this case).

```bash
export FLASK_APP=main.py
```

Check the env var:

```bash
echo $FLASK_APP
$ main.py
```

And then you can run your app:

```bash
flask run
```

Now you can send a request to check your app:

```bash
curl http://127.0.0.1:5000/
```

To stop, just press `CTRL + c`
