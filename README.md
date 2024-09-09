# Bandit Scan

Run Python [Bandit](https://github.com/PyCQA/bandit) scan on your codebase.

## About

Bandit is a tool designed to find common security issues in Python code. This action will run Bandit on your codebase. The results of the scan will be found under the Security tab of your repository.

## Usage

To run a bandit scan include a step like this:

```yaml
    uses: reactive-firewall/python-bandit-scan@v2.1
        with: # optional arguments
        # Github token of the repository (automatically created by Github)
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }} # Needed to get PR information.
        path: "."
        level: high
        confidence: high
        # exit with 0, even with results found
        exit_zero: true # optional, default is DEFAULT
```

## Inputs

### `path`

**Optional** The path to run bandit on

**Default** `"."`

### `level`

**Optional** Report only issues of a given severity level or higher. 
Can be LOW, MEDIUM or HIGH. Default is UNDEFINED (everything).

**Default** `"UNDEFINED"`

### `confidence`

**Optional** Report only issues of a given confidence level or higher. 
Can be LOW, MEDIUM or HIGH. Default is UNDEFINED (everything).

**Default** `"UNDEFINED"`

### `excluded_paths`

**Optional** Comma-separated list of paths (glob patterns supported) to exclude from scan 
(note that these are in addition to the excluded paths provided in the config file) (default is from the Bandit itself)

**Default** `".svn,CVS,.bzr,.hg,.git,__pycache__,.tox,.eggs,*.egg"`

### `exit_zero`

**Optional** Exit with 0, even with results found (set `"true"` to use it)

### `skips`

**Optional** Comma-separated list of test IDs to skip

### `ini_path`

**Optional** Path to a .bandit file that supplies command line arguments

## Outputs

The action will create an artifact containing the sarif output.

## Credits

- :bow: This action is based on [bandit-action](https://github.com/mdegis/bandit-action) by [Melih Değiş](https://github.com/mdegis/).
- :bow: This action is _also_ based on [python-bandit-scan](https://github.com/shundor/python-bandit-scan) by [shundor](https://github.com/shundor).
- :bow: This fork includes fixes proposed by [Kenta Nakase](https://github.com/parroty) and [Thiago Grisolfi](https://github.com/Grisolfi) ... 🎉 but automated by @dependabot

