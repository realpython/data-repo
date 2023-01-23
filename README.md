# data-repo

This package provides a namespace intended for data files.

It let's you have a common package to read data files, but with the ability to distribute the namespace over multiple packages.

For example, if you have various data files which are very large (in the order of hundreds of megabytes or larger), you can divide the data files into different packages, but that will be callable from the same namespace in your Python code.

That means you could install the data packages you need from PyPI:

```shell
$ python -m pip install data-repo-cars data-repo-countries
```

Once installed, you can just import `read` from `data_repo` and all your data sets will be available, if there's a reader registed for the datatype:

```python
>>> from data_repo import read
>>> read.data("cars")
...
>>> read.data("countries")
...
```
