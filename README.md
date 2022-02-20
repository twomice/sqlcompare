# sqlcompare

CLI utility to compare database before and after changes; it works about like this:
```
$ sqlcompare my_database
'Before' snapshot has been taken.
Make your DB changes in the browser or elsewhere, then strike Enter here to continue with the 'after' snapshot.
```

Make whatever changes you want in your big bad complicated web app, CMS, or whatever.
Come back to the terminal and strike Enter.

```
24c24
< INSERT INTO `test1` (`test`) VALUES (3);
---
> INSERT INTO `test1` (`test`) VALUES (4);
```

Also try `-w` for a word-based diff using git (colored red for deletions and green for insertions); useful for rows that contain thousands of characters of data.

```
@@ -24 +24 @@ LOCK TABLES `test1` WRITE;
INSERT INTO `test1` (`test`) VALUES ([-3-]{+4+});
```

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