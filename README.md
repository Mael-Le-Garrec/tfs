# TFS-Pandas

This package provides reading and writing functionality for **table format system (tfs)** files. 

## Getting Started

### Prerequisites

The package depends heavily on `pandas` and also on `numpy`, so these packages need
to be installed in your python environment.

### Installing

Installation is easily done via `pip`. The package is then used as `tfs`.

```
pip install tfs-pandas
```

Example:

```
import tfs

data_frame = tfs.read('path_to_input.tfs', index="index_column")
tfs.write('path_to_output.tfs', data_frame, save_index="index_column")
```
## Description

Reading and writing capabilities for [tfs-files](http://mad.web.cern.ch/mad/madx.old/Introduction/tfs.html)
are provided by this package. The files are read into special `pandas` `Dataframes`, called `TfsDataFrames`,
which in addition to the normal behaviour attach an `OrderedDict` of headers to the `DataFrame`.


## Known Issues

- Creating a new `DataFrame` by combining multiple `TfsDataFrame`,
for example via `pandas.DataFrame.append()` or `pandas.concat()`, 
will convert the `TfsDataFrame` back to a `DataFrame` and lose therefore the headers.

## Authors

* **Jaime** - *Initial work* - [jaimecp89](https://github.com/jaimecp89)
* **Lukáš** - *Initial work* - [lmalina](https://github.com/lmalina)
* **Josch** - *Publishing* - [JoschD](https://github.com/JoschD)
* **pyLHC/OMC-Team** - *Working Group* - [pyLHC](https://github.com/orgs/pylhc/teams/omc-team)


## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

