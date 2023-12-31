# nnapec
![CI](https://github.com/grburgess/nnapec/workflows/CI/badge.svg?branch=master)
![PyPI](https://img.shields.io/pypi/v/nnapec)
![PyPI - Downloads](https://img.shields.io/pypi/dm/nnapec)

![alt text](https://raw.githubusercontent.com/grburgess/nnapec/master/docs/media/logo.png)


An emulator for the APEC model


* Free software: GNU General Public License v3
* Documentation: https://jmichaelburgess.com/nnapec


## Installation

```bash
pip install nnapec
```

## How to

The APEC model is incredibly slow. This is not fun.

Here we provide an neural net emulator that can be used with `astromodels` and
`3ML` which is much faster than using `pyatomdb`.

```python
import numpy as np

from nnapec import get_apec_model

# get an instance of the apec model
# multiple instances can be used

nn_apec = get_apec_model()


nn_apec.redshift = 1.
nn_apec.redshift.fix = True
nn_apec.kT = 3.
nn_apec.abund = 0.3

energies = np.geomspace(0.1, 10., 1000)

photon_flux = nn_apec(energies)





```


* TODO
  *  Currently the model is trained with the `AG89` abundances
  *  Will train more models if needed

## Credits

