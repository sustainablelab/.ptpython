# Put `config.py` in `.config/ptpython`

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
