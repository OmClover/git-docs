**\#!/bin/bash**


**USER\_TOKEN ="ghp\_nm77YdDK9fso8ZMSaUR5zVMMeaaUgY1g\*\*\*\*"**


**if ! command gh auth status &\> /dev/null; then**

**echo "You are not logged in"**

**gh auth login --hostname github.com --with-token \<\<\< "$USER\_TOKEN"**

**echo "You are logged in "**

**gh repo list**

**else**

**gh repo list**

**fi**


- Save above code in .sh file

- Give this file execution permission by command chmod +x filename.sh

- Run it by command  ./filename.sh

- It’ll automatically ffirst check whether user is logged in or not using gh auth status and if not then login using USER\_TOKEN we gave and fetch repo lists using gh repo list


------------------------------------------------------------------------------------------------------------------------


- We can automate the execution of this file like at a specific time of the day the file will execute

- This can be done by creating crontab

- Open and edit crontab file using command → crontab -e

- 55 16 \* \* \* /home/clover/scripts/list\_all\_repos.sh \>\> /home/clover/scripts/repo-list.txt 2\>&1

- Save above line in cron file, Output of first .sh file will append in repo-list.txt file at mentioned time. 

- 2\>&1 → redirects **Standard Error** (stream 2) into **Standard Output** (stream 1) so that normal text and error messages are saved into the exact same log file.

- \* \* \* \* \* /path/to/command

- │  │  │  │  │

- │  │  │  │  └─ Day of the week (0 - 6) (Sunday to Saturday)

- │  │  │  └──── Month (1 - 12)

- │  │  └─────── Day of the month (1 - 31)

- │  └────────── Hour (0 - 23)

- └───────────── Minute (0 – 59)

- Check status using command → sudo service cron status

- Can start manually using command → sudo service cron start

- `crontab -l` →  Quickly view your active cron schedule without opening the text editor.


