# `plistlib_mod`

A slightly enhanced/modified version of the [plistlib](https://docs.python.org/3/library/plistlib.html) module from the Python standard library.

## Features

At the moment,
`plistlib_mod` is identical to the `plistlib` standard library module from Python 3.10.6.

## Installation

`plistlib_mod` is compatible with Python 3.10 or later.

`plistlib_mod` is not released on PyPI yet.
Once it is released,
you will be able to use the package `plistlib_mod` as a dependency.

## Usage

`plistlib_mod` is nearly identical to the standard `plistlib` module.
The recommended way to use it is:

```python
import plistlib_mod as plistlib
```

If appropriate,
you can also conditionally fall back to the standard `plistlib` module
in case `plistlib_mod` isn't available.
If you do this,
make sure that your code can handle `plistlib_mod`'s enhancements being unavailable!

```python
try:
    import plistlib_mod as plistlib
except ModuleNotFoundError:
    import plistlib
```

## License

Like Python itself,
`plistlib_mod` is licensed under the Python Software Foundation License Version 2.
See the [LICENSE](./LICENSE) file for details.

## Changelog

### Version 0.1.0 (next version)

* Initial release.
* Matches `plistlib` from Python 3.10.6.
