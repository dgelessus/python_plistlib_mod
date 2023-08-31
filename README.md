# `plistlib_mod`

A slightly enhanced/modified version of the [plistlib](https://docs.python.org/3/library/plistlib.html) module from the Python 3.11 standard library,
backported to Python 3.4 and later.

## Features

At the moment,
`plistlib_mod` matches the `plistlib` standard library module from Python 3.11.5,
but is compatible with Python 3.4 and later.
In particular,
it includes the following features and fixes,
which are otherwise not available on older Python versions:

* Fix typo in error message in plistlib ([GH-97540](https://github.com/python/cpython/pull/97540)) (from 3.11+, 3.10.8)
* [bpo-42249](https://bugs.python.org/issue42249): Fix writing binary Plist files larger than 4 GiB. ([GH-23121](https://github.com/python/cpython/pull/23121)) (from 3.10+, 3.9.1, 3.8.7)
* [bpo-42103](https://bugs.python.org/issue42103): Improve validation of Plist files. ([GH-22882](https://github.com/python/cpython/pull/22882)) (from 3.10+, 3.9.1, 3.8.7, 3.7.10, 3.6.13)
* [bpo-41491](https://bugs.python.org/issue41491): `plistlib`: accept hexadecimal integer values in xml plist files ([GH-22764](https://github.com/python/cpython/pull/22764)) (from 3.10+, 3.9.1, 3.8.7)
* [bpo-42051](https://bugs.python.org/issue42051): Reject XML entity declarations in plist files ([#22760](https://github.com/python/cpython/pull/22760)) (from 3.10+, 3.9.1, 3.8.7, 3.7.10, 3.6.13)
* [bpo-26707](https://bugs.python.org/issue26707): Enable `plistlib` to read UID keys. ([GH-12153](https://github.com/python/cpython/pull/12153)) (from 3.8+)
* [bpo-32072](https://bugs.python.org/issue32072): Fix issues with binary plists. ([#4455](https://github.com/python/cpython/pull/4455)) (from 3.7+, 3.6.4, 3.5.5, 3.4.8)
* [bpo-31897](https://bugs.python.org/issue31897): Convert unexpected errors when read bogus binary plists into `InvalidFileException`. ([#4171](https://github.com/python/cpython/pull/4171)) (from 3.7+, 3.6.4)
* [bpo-28321](https://bugs.python.org/issue28321): Fixed writing non-BMP characters with binary format in `plistlib`. (from 3.5.3+)
* [bpo-27109](https://bugs.python.org/issue27109): Add `InvalidFileException` to `__all__`, by Jacek Kołodziej (from 3.6+)
* [bpo-26711](https://bugs.python.org/issue26711): Fixed the comparison of `plistlib.Data` with other types. (from 3.5.2+)
* [bpo-26709](https://bugs.python.org/issue26709): Fixed Y2038 problem in loading binary PLists. (from 3.5.2+)
* [bpo-21888](https://bugs.python.org/issue21888): plistlib's `load()` and `loads()` now work if the fmt parameter is specified. (from 3.4.2+)
* [bpo-21538](https://bugs.python.org/issue21538): The `plistlib` module now supports loading of binary plist files when reference or offset size is not a power of two. (from 3.4.2+)

The following deprecated APIs have been removed,
like in newer Python versions:

* [bpo-36409](https://bugs.python.org/issue36409): Remove old `plistlib` API deprecated in 3.4 ([GH-15615](https://github.com/python/cpython/pull/15615)) (removed in 3.9)
* [bpo-29196](https://bugs.python.org/issue29196): Removed old-deprecated classes `Plist`, `Dict` and `_InternalDict` ([#488](https://github.com/python/cpython/pull/488)) (removed in 3.7)

## Installation

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
* Based on `plistlib` from Python 3.11.5,
  with small compatibility changes.
