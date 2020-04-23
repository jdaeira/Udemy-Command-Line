#### Wildcard Notes

```
looking for files with Wildcards
looking for files with number 1-3
ls -la file[1-3].txt
```

```
mkdir -p Folder1/Folder2/Folder3
creates directories in each of the created folders
```

```
Will make directories for each month with year
mkdir {jan,feb,mar,apr,may,jun,jul,aug,sep,oct,nov,dec}_{2017,2018,2019,2020,2021,2022}
```

```
Will make 100 files starting with file1-100 into each of the directories
touch {jan,feb,mar,apr,may,jun,jul,aug,sep,oct,nov,dec}_{2017,2018,2019,2020,2021,2022}/file{1..100}
```

```
touch file{A,B,C}.txt or file{A..C}.txt
creates fileA.txt fileB.txt fileC.txt
```

#### Nano Notes

```
Nano's configuration file is in /etc/nanorc
Copy in Nano is: Alt+Shift+^
The "M" key in Nano is the "Alt" key
```

#### Locate Notes

```
will locate files / -i searches for case insesitive / --limit will look for number of files
/ 10 files in this case
must run "sudo updatedb" to locate recently added files / updatedb is updated daily
locate -i --limit 10 *.conf
locate -S : shows the stats on the database
```

#### Find Notes

```
find . : looks for files in that directory only with maximum depth
find . -maxdepth 1 : only shows what's in the current directory
find . -type f : searches only for files
find . -type d : searches only for directories
find . -maxdepth 2 -type f : give the -maxdepth option first
find . -maxdepth 5 -name "*.txt" : looks for a file name ending in .txt : -name is case sensitive
find . -maxdepth 5 -name "?.txt" : the "?" represents one character "??" would represent 2
find . -maxdepth 5 -iname "?.txt" : iname is case insensitive
sudo find / -type f -size +100k : -size searches for files larger than specified
sudo find / -type f -size +100k -size -5M : file sizes greater than 100 kilobytes and less then 5 megabytes
sudo find / -type f -size -100k -o -size +5M : -o in the middle is the or command
find . -type f -size +1G -exec ls -la {} \; : Will find files larger than 1GB and then list them
-ok instead of -exec will ask if it's ok to do something
{} represents all the files or folders
\; end the command after -exec
```

#### Viewing Files
```
tac is like cat, but reverses files vertically
rev reverses the words in a file by line horizontally
less command to make a long list easier to view
```

#### Sorting
```
sort words.txt : sorts the file alpabetically
sort -n numbers.txt : -n is needed to sort numbers
sort -n -u number0-9.txt : sorts only the unique numbers
ls -l /etc | head -n 20 | sort -k 5nr : sorts the 5th column in reverse order
ls -lh /etc | head -n 20 | sort -k 5hr : "h" option reads human readable data
ls -lh /etc | head -n 20 | sort -k 6M : "M" option is for the month
sort -r : sorts things in reverse
```

#### Searching File Content
```
grep -c e file1.txt : Will search how many lines "e" appears
grep -i gadsby gadsby_manuscript.txt : Will search for gadsby lower or upper case
grep -v e gadsby_manuscript.txt : Will search all the lines that don't have letter "e"
ls -lF / | grep root
```

#### Compressing and Archiving
```
tar -cvf ourarchive.tar file[1-3].txt : to create a .tar archive
-c : to create files
-v : verbose
-f : to create files
-t : test label to check inside
-x : to extract files
-j : compress to a bzip2 file
-J : is for XZ file
-z : compress to a gzip file
tar -tf ourarchive.tar : to check what is inside a .tar file
tar -xvf ourarchive.tar : to extract the files in the .tar archive
gzip ourarchive.tar : to compress files using gzip (.gz)
gunzip ourarchive.tar.gz : to uncompress the gzip (.gz)
bzip2 ourarchive.tar : to compress files using bzip2 (.bz2)
bunzip2 ourarchive.tar.bz2 : to uncompress the bzip2 (.bz2)
bzip2 is better for larger files like video
zip ourthing.zip : to create a zip file
tar -cvzf ourarchive.tar file[1-3].txt : compress to a gzip file
tar -xvzf ourarchive.tar file[1-3].txt : extract from a gzip file. Just change the -c to -x
```

#### Assignment Solution

##### Task 1
```
mkdir super_secret_stuff
cd super_secret_stuff
touch top_secret.txt
sudo update.db
locate top_secret.txt > secret_place.txt
```

##### Task 2
```
sudo find / -maxdepth 4 -type f -size +1M -exec ls -lh {} \; | sort -k 5hr > filesizes.txt
```