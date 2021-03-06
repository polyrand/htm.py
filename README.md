# htm.py ![Tests](https://github.com/jviide/htm.py/workflows/Tests/badge.svg) [![PyPI](https://img.shields.io/pypi/v/htm.svg?color=blue)](https://pypi.org/project/htm/)

A Python version of [developit/htm](https://github.com/developit/htm) - JSX-like syntax in plain ~~JavaScript~~ Python.

![](https://user-images.githubusercontent.com/19776768/59420458-99d60000-8dd5-11e9-9d29-02fff6c83a55.png)

## Documentation

The main documentation of this module is located at https://jviide.github.io/htm.py/.

## Installation

```sh
$ pip3 install htm
```

## Usage

```py
from htm import htm

@htm
def html(tag, props, children):
    return tag, props, children

a = 1
b = {"bar": 100}
c = "span"
d = "world"

html("""
  <div foo={a+2} ...{b}>
    <{c}>Hello, {d}!<//>
  </div>
""")
# ('div', {'foo': 3, 'bar': 100}, [('span', {}, ['Hello,', 'world', '!'])])
```

## Development

To install locally:

```shell script
$ pip install -e .
```

If you want to run tests and build the Sphinx docs and their examples...that runs into [a problem with hyperpython's transitive dependencies](https://github.com/ejplatform/hyperpython/issues/4).
Thus: 

```shell script
$ pip install toolz
$ pip install sidekick
$ pip install -e .[docs]
```


### Running Tests

```sh
$ python3 -m unittest discover -s tests
```

### Building Docs

Documentation is available in the `docs` directory.
First install the dependencies then build the docs:

```shell script
$ pip install -e .[docs]
$ cd docs
$ sphinx-build -b html . _build
```

## License

This library is licensed under the MIT license. See [./LICENSE](./LICENSE).
