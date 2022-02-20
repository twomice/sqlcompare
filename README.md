# sqlcompare

CLI utility to compare database before and after changes.

## Installation

Copy config.sh.dist to config.sh and edit per comments in that file.

## Usage
```
Usage: sqlcompare [options] DATABASE_NAME
  Compare mysql database contents before and after changes.
  Will prompt for required config if not provided.
  DATABASE_NAME: name of mysql database to examine
  Options:
    -i: (string) Space-delimited list of table names to ignore.
    -c: (string) Full system path to additional config file; loaded after
        config.sh, it can override those configs.
    -w: (null) Print word-based diff (instead of default line-based)
    -h: (null) Display this help message.

See also: config.sh.
```