# Pipe in Linux

- Pipes are used to redirect a stream from one program to another program.

- The output of one command is redirected to input of another command.

```sh

# Find number of files in a directory
# `ls` is used to list contents of a directory
# The `-1` option tells ls to display each filename in a separate line, instead of the default multi-column format.
# The output from the first command (ls -1) is sent as input to the second command.
# `wc` stands for "word count." It's a handy tool for counting lines, words, and characters in text files.
# The -l option gives the line count.
ls -1 | wc -l

# Combine 2 files using cat and sort it
cat names.txt countries.txt | sort

# Find unique records from a file
cat names.txt | sort | uniq

# How to only see line 30-37 in a file containing 100 lines?
cat users-data.csv | head -38 | tail -7

netstat | less

netstat | more
```

## `tee` command
