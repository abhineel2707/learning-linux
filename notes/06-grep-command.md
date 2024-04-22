# `grep` Command

- `grep` command searches for a particular string/keyword from a file and prints the line matching the pattern.

- It checks line by line and prints lines matching given pattern.

- `grep` stands for "**Global Regular Expression Print**".

- Use `grep` when:

  - We need to find text inside files (logs, code, documents, etc).

  - We want to see if a specific word or pattern appears in a file.

- `grep` command syntax: `grep [OPTION] Pattern [File]`

```csv
id,firstname,lastname,email,profession
100,Mady,Cloris,Mady.Cloris@yopmail.com,police officer
101,Nita,Eiser,Nita.Eiser@yopmail.com,worker
102,Ada,Rosette,Ada.Rosette@yopmail.com,worker
103,Demetris,Teryn,Denetris.Teryn@yopmail.com,police officer
104,Mahalia,Sperling,Mahalia.Sperling@yopmail.com,firefighter
105,Deirdre,Lemuela,Deirdre.Lemuela@yopmail.com,firefighter
106,Cyndie,Chem,Cyndie.Chem@yopmail.com,police officer
107,Modestia,Engdahl,Modestia.Engdahl@yopmail.com,doctor
108,Jaime,Corabella,Jaime.Corabella@yopmail.com,police officer
109,Gusty,Jehu,Gusty.Jehu@yopmail.com,doctor
```

```sh
# Search Nita in csv1
grep Nita csv1

# Ignore case while searching
grep -i nita csv1

# Search everything except given pattern
grep -v Nita csv1
# OR add ignore case
grep -iv nita csv1

# Print count of given work in file
grep -c Nita csv1

# Search exact match of given keyword in a file
grep -w Nita csv1

# Print match with line number of given keyword in a file
grep -n Nita csv1

# Search given keyword in multiple files
grep name file1 file2 csv1

# Suppress file names while searching a given keyword in multiple files
grep -h name file1 file2 csv1

# Search multiple keywords in a file
grep -e Nita -e Jaime csv1
# OR Print line number as well with multiple keywords
grep -n -e Nita -e Jaime csv1

# Search multiple keywords in multiple files
grep -e Abhineel -e Baburao file1 file2

# Print file names that match the given keyword
grep -l Jaime csv1
grep -l -e Abhineel -e Baburao csv1 file1 file2

# Get keywords/pattern from a file and match with another file
grep -f keyword.txt csv1 file1 file2

# Print matching line that starts with given keyword
grep "^103" csv1

# Print matching line that ends with given keyword
grep "doctor$" csv1

# Suppose we have 100s of files in a directory and we need to search keyword in all files
grep -R -f keyword.txt ../practise-grep/

# We can use egrep command for multiple keyword search
egrep "Nita|Abhineel|Baburao" csv1 file1 file2

# If we just want to search and don't want to print on terminal. Usually used in scripting for conditions
grep -q Nita csv1
# and then check exit status using
echo $? # 0 means success and 1 means failure

# If while searching we get an error, -q will print error. To suppress error we use -s
grep -qs Nita csv

# If we want to search our file in a directory containing multiple files
ls | grep rs

```
