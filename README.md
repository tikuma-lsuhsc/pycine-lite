# pycine-lite

[![PyPI](https://img.shields.io/pypi/v/pycine-lite)](https://pypi.org/project/pycine-lite/)
![PyPI - Status](https://img.shields.io/pypi/status/pycine-lite)
![PyPI - Version](https://img.shields.io/pypi/pyversions/pycine-lite)
![License](https://img.shields.io/github/license/tikuma-lsuhsc/pycine-lite)

Reading Vision Research .cine files in Python

This package is a feature-stripped version of [`pycine`](https://github.com/ottomatic-io/pycine)
to minimize the package dependencies. Specifically, the `cli` and `color` submodules 
have been removed from the `pycine` package.

## Installation

```
pip install -U pycine-lite
```

## Example usage

`pycine-lite` distro package is module-compatible with the `pycine` package.

### Read `n`-frames from from `frm0`

```python
from pycine.raw import read_frames

raw_images, setup, bpp = read_frames(cine_file, start_frame=frm0, count=n)
```

### Iteratively read frames

Suppose you want to run `process_frame()` function on every frame.

```python

from pycine.raw import read_header, frame_reader

header = read_header(cine_file)

for frm in frame_reader(cinefile, header, start_frame=frm0, count=n):

    process_frame(frm)
```
