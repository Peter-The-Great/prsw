# PRSW: Python RIPE Stat Wrapper

[![Latest Version](https://img.shields.io/pypi/v/prsw.svg)](https://pypi.python.org/pypi/prsw)
[![Supported Python Versions](https://img.shields.io/pypi/pyversions/prsw)](https://pypi.python.org/pypi/prsw)
[![GitHub Actions Tests](https://github.com/jvoss/prsw/actions/workflows/tests.yml/badge.svg)](https://github.com/jvoss/prsw/actions/workflows/tests.yml)
[![Coveralls](https://coveralls.io/repos/github/jvoss/prsw/badge.svg?branch=master)](https://coveralls.io/github/jvoss/prsw?branch=master)
[![Documentation Status](https://readthedocs.org/projects/prsw/badge/?version=latest)](https://prsw.readthedocs.io/en/latest/?badge=latest)

PRSW, the RIPE Stat Wrapper, is a Python package that allows for simple access
to the [RIPEstat Data API](https://stat.ripe.net/docs/data-api/ripestat-data-api). 

## Quickstart

RIPEstat can be instantiated with a few options. For details see the
[documentation](https://prsw.readthedocs.io).

1. Instantiate a basic instance of RIPEstat:

```python
import prsw

ripe = prsw.RIPEstat()
```

2. With the `ripe` instance you can interact with the RIPEstat API as python
   objects:

```python
# Find all announced prefixes for a Autonomous System
prefixes = ripe.announced_prefixes(3333)

# Interact with the looking glass
for collector in ripe.looking_glass('140.78.0.0/16'):
print(collector.location)

for peer in collector.peers:
    print(
        peer.asn_origin,
        peer.as_path,
        peer.community,
        peer.last_update,
        peer.prefix,
        peer.peer,
        peer.origin,
        peer.next_hop,
        peer.latest_time
    )

# Check RPKI validation status
print(ripe.rpki_validation_status(3333, '193.0.0.0/21').status)
```

Please see the [documentation](https://prsw.readthedocs.io) for more options.

## Installation

### Via `pip`:

```
pip install prsw
```

Install the latest development version:

```
pip install --upgrade https://github.com/jvoss/prsw/archive/master.zip
```

### Via `uv`:

```
uv add prsw
```

Install the latest development version:

```
uv add git+https://github.com/jvoss/prsw.git
```

## Contributing

Contributions are encouraged. Please see [CONTRIBUTING.md](CONTRIBUTING.md) for
details.

## Acknowledgements

Inspiration for several elements of this project originally came from 
[PRAW](https://github.com/praw-dev/praw), the Python Reddit API Wrapper.

## License

PRSW is licensed under the [Simplified BSD License](LICENSE.txt).
