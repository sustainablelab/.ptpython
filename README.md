# Windows: Put `config.py` in appdirs folder

Open a Python REPL and use `appdirs` to find out where the
`ptpython` *config* files should go:

```python
>>> import appdirs
>>> appdirs.user_config_dir("ptpython","prompt_toolkit")
```

Change pwd to this directory. Then use wget to download the config file
from this repo as a starting point.

## Download from GitHub without cloning

Use `wget` on the raw file URL.

`wget` the raw file link
```bash
$ wget https://raw.githubusercontent.com/sustainablelab/.config-ptpython/master/Windows/config.py
```

`wget` is not part of the base Cygwin install. Run the Cygwin
package manager to install it.

Click on the `Raw` button on the GitHub site to get the URL to
the raw file (otherwise `wget` downloads the HTML page).

## Edit the config
Create a bash variable to this path. Here is how that looks on
Cygwin:

```bash
 # ~/.bashrc

 # Window ptpython config file
ptpythonw_config="/cygdrive/c/Users/username/AppData/Local/prompt_toolkit/ptpython/config.py"
 # Make accessible in Vim as $ptpythonw_config
export ptpythonw_config
```

Example quickly editing the config with Vim:

```bash
$ vim $ptpythonw_config
```

## Navigate to config folder
Example using this variable to quickly navigate to the folder
that has the `ptpython` config:

```bash
$ cd "$(find $ptpythonw_config -printf '%h')"
```

# Cygwin: Put `config.py` in `.config/ptpython`

Put `config.py` in `$HOME/.config/ptpython`. The `config` is
picked up by default.

Start `ptpython`:

```bash
$ ptpython
```

or

```bash
# Specify my Cygwin installation:
$ ptpython3.7
```

This default path *used to be* `$HOME/.ptpython/config.py`.

The old default path works, but I get warning message that it is
deprecated.

# Or put `config.py` anywhere and use the `--config-file=` flag

Specify a `config.py` file using the `--config-file` flag:

```bash
$ ptpython --config-file=~/project-foo/.ptpython/config.py
```
