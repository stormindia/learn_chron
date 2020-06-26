┌───────────── minute (0 - 59) <br/> 
│ ┌───────────── hour (0 - 23) <br/>
│ │ ┌───────────── day of month (1 - 31) <br/>
│ │ │ ┌───────────── month (1 - 12) <br/>
│ │ │ │ ┌───────────── day of week (0 - 6) (Sunday to Saturday; <br/>
│ │ │ │ │                                      7 is also Sunday on some systems) <br/>
│ │ │ │ │<br/>
│ │ │ │ │<br/>
* * * * * <command>

#### To understand how collisions are resolved between day of month and day of week, refer this -> 
https://stackoverflow.com/questions/34357126/why-crontab-uses-or-when-both-day-of-month-and-day-of-week-specified<br/>
https://crontab.guru/

#### Tutorials - 
https://www.youtube.com/watch?v=QZJ1drMQz1A


#### On WSL run this(set in root bashrc as well) to start cron services ->
sudo service cron start

usage:  crontab [-u user] file <br/>
        crontab [ -u user ] [ -i ] { -e | -l | -r } <br/>
                (default operation is replace, per 1003.2) <br/>
        -e      (edit user's crontab) <br/>
        -l      (list user's crontab) <br/>
        -r      (delete user's crontab) <br/>
        -i      (prompt before deleting user's crontab) <br/>


#### Cron Permissions 
 To run sudo commands in cron
 use sudo crontab -e
 /etc/cron.allow – if the cron.allow exists, it must contain the user’s name for the user to use cron jobs.
 /etc/cron.deny – if the cron.allow file doesn’t exist but the cron.deny file does, then to use cron jobs the user must not be listed in the cron.deny file.

#### Sample crontab

#### Empty temp folder every Friday at 5pm
0 5 * * 5 rm -rf /tmp/*

#### Backup images to Google Drive every night at midnight
0 0 * * * rsync -a ~/Pictures/ ~/Google\ Drive/Pictures/

#### Comma operator to run at midnight at first and 15th of every month
0 0 1,15 * * <command>

#### to run a command at every 10 minutes of every day
*/10 * * * * <command>

#### range operator - every hour from midnight to 5 AM
0 0-5 * * * <command>


