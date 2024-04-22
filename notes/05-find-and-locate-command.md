# find And locate Command

| `find`                                                                                                 | `locate`                                                 |
| ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------- |
| Scans the entire file system in real time                                                              | Uses a pre-built database of file locations              |
| Slower, especially on larger file systems                                                              | Faster, especially for broad searches                    |
| More flexible, with various search criteria like file type, file name, size, location or date modified | Limited to searching by file name (or partial file name) |
| No database needed                                                                                     | Relies on an updated database (`updatedb` command)       |
| Needs exact file name                                                                                  | Can work with partial file names                         |

```sh
# Find in the current directory a file with name "myfile"
find . -name myfile

find . -type f -name myfile

find . type -d -name myfile

locate myfile

locate -c myfile

# Partial file name
locate myfil
```

## `find` command in detail

`find [options] [path] [expression]`

```sh

# Search a file based on their size
# M for MB, k for KB, G for GB c for bytes
find /path/ -size 50M

# How to find only files or directories in a given path?
# -type f for files, d for directory, l for symbolic link, b for block device, s for socket
find . -type f
find . -type d
find . -type l
find . -type b
find . -type s

# How to search file based on name?
# We need to provide exact name
find . -name a123

# How to ignore upper and lower case in file name while searching files?
find . -iname A123

# How to search files for a given user only?
find . -user abhineel

# How to search files based on inode number?
ls -li # list files with inode number
find . -inum 2361010

# How to search a file based on number of links?
find /path/ -links <no of links>

# How to search a file based on their permissions?
find /path/ -perm /u=r # show files where user has read permission
find /path/ -perm 777

# How to search all files that start with letter a?
find /path/ -iname a*
find . -iname a*

# How to search all files which are modified/created after last.txt file?
find /path/ -newer last.txt

# How to search all empty files in a given directory?
find /path/ -empty

# How to search all empty files in a given directory and delete them at same time?
find /path/ -empty -exec rm {} \;
touch empty-file # create a file with name empty-file
find . -name empty* -exec rm {} \;

# How to search all files whose size are between 1-50MB?
find /path/ -size +1M -size -50M

# How to search 15 days old file?
find /path/ -mtime 15

```
