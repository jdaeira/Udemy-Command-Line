#### Adding to PATH
```
add PATH of scripts to the .bashrc file
PATH="$PATH:$HOME/bin" : bin folder are where the scripts are located
Can run a bash script from anywhere after that
```

#### Cron Jobs
```
crontab -e
1st column : minutes of the hour
2nd column : hour ( 24 hour )
3rd column : day of the month
4th column : month (JAN,DEC)
5th column : day of the week (0 - 6) (Sunday - Saturday) 
* : any value
, : value list seperator
/ : step value
0,15,30,45 or */15 : run every 15 minutes
```

#### Assignment Solution

##### Task 1
```
!/bin/bash

echo "I am hungry, Feed me data." > demands.txt
date >> demands.log
```

##### Task 2
```
*      *        *      *      *     bash ~/hungry.sh
```