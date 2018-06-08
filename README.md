# mypy-pycharm

mypy-pycharm is a wrapper around mypy that formats file paths in the mypy output in a way that Pycharm can parse. Notabliy adding absolute path names. This allows you to go to the error directly by clicking on the provided link.

The tool accepts all standard mypy options and passes them through to mypy but also expects an additional final argument which is the absolute path to the directory you are running mypy in.

Shamelessly inspired by [pylint-pycharm](https://github.com/tgamauf/pylint-pycharm) <3!

## Setup
* Install mypy via pip: `pip install --user mypy`
* Install mypy-pycharm:
    ```
    git clone https://github.com/mleonard87/mypy-pycharm
    ```
* Setup mypy-pycharm as an external tool in Pycharm:
    * `File\Settings`, then `Tools\External Tools`
    * Add tool by pressing `+`
    * Use the following settings:
        * Program: <path-to>/mypy-pycharm/scripts/mypy-pycharm
        * Arguments: `$Sourcepath$ --ignore-missing-imports --follow-imports=skip $ProjectFileDir$`
        * Working directory: `$ProjectFileDir$`
        * Advanced Options\Output Filters: `$FILE_PATH$:$LINE$:.*`

After setup you can execute mypy-pycharm through `Tools\External Tools\mypy
