# fgslpyrest

Python component to make HTTP RESTful requests.

## How to install

```shell
pip install fgslpyrest
```

## Using the component 

### Making a HTTP GET request in the terminal

The sequence of commands below make a HTTP GET request and check if the response has the word "German". The response, in this case, is HTML. The last parameter enables verbose output.

```shell
$ python
>>> from fgslpyrest.http.Rest import Rest
>>> rest = Rest()
>>> response = rest.doGet([],"https://time.is/pt_br/UTC",200,True)
>>> print(response.find("German"))
```

The next sequence of commands make a HTTP request which returns a JSON object.

```shell
$ python
>>> import json
>>> from fgslpyrest.http.Rest import Rest
>>> rest = Rest()
>>> response = rest.doGet([],"https://reqres.in/api/users/2",200)
>>> user = json.loads(response)
>>> print(user["data"]["email"])
```

## For developers

* **PKG-INFO** describes the package in a summarized way.
* **MANIFEST.in** defines which files will be included into the package.
* **pyproject.toml** defines the general packaging information.

More information at https://packaging.python.org/en/latest/tutorials/packaging-projects/

## Running the unit tests

```shell
python -m unittest tests/resttest.py 
```

### Building the package

```shell
python -m build --sdist .
```

Requires `build` module. You can install it using `pip install build`.

### Upload the package to PyPI

```shell
twine upload dist/*
```

## Troubleshooting

If you try to install and receive a error message with this fragments:

`filename has 'fgslpyrest', but metadata has 'unknown'`

`ERROR: No matching distribution found for fgslpyrest`

Then run this command:

```shell
pip3 install --upgrade pip
```

And try to install again.
