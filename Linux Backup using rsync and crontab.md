## Automating the Linux Backup using rsync and crontab
  - Prepared by Samdup

>You should be logged in as root or use su (or sudo)
>Location of the crontab  /etc/crontab or /etc/cron/crontab


- crontab : cron table

- To view ```crontab -l```


|Field|Description|Allowed Value|
|:---:|:---:|:---:|
|MIN|Minute field|0-59|
|HOUR|Hour field|0-24|
|DOM|Day of Month|1-31|
|MON|Mon field|1-12|
|DOW|Day of Week|0-6|
|CMD|Command|Any command to be executed|

Note: Time 24 hours format

#### Example
30 08 10 06 \* /home/samdup/full-backup-cmd

#### What is incremental backup ?

- Full Backup       
- Incremental Backup  
- Differential Backup

#### Exercise
- To run the rsync-with-backup command from the previous section every morning at 4:30 AM, for example, edit the root cron table: (as root)
- ```sudo crontab -e```
- Add this line  
  - ```20 4 * * * rsync -a --delete /path/of/source/ /path/to/destination/```

- Our case:
- source location: /home/samdup/source/
- rsync location:  /usr/bin/rsync


- Note: Root will receive the output by email. Don't copy that example verbatim, though; you should use full path names (such as /usr/bin/rsync and /home/source/) to remove any ambiguity.

- 30th minute
- 08 08 AM
- 10 10th Day
- 06 June
- \* Every day of the week

### Cron special keywords and it's meaning

|Keyword| Equivalent|
|:---:|:---:|
|@yearly| 0 0 1 1 \*|
|@daily | 0 0 \* \* \*|
|@hourly| 0 \* \* \* \*|
|@reboot| run at startup|

### [Watch the tutorial in Tibetan Language](https://youtu.be/465clmITDec)

### Reference
[1](https://www.geeksforgeeks.org/crontab-in-linux-with-examples/),
[2](http://www.admin-magazine.com/Articles/Using-rsync-for-Backups),
[3](https://askubuntu.com/questions/476041/how-do-i-make-rsync-delete-files-that-have-been-deleted-from-the-source-folder),
[4](https://searchdatabackup.techtarget.com/definition/differential-backup),
[5](http://www.mikerubel.org/computers/rsync_snapshots/)\*\*\*.

[Find me on Facebook](http://facebook.com/epotala)   
[Youtube tutorials](https://www.youtube.com/channel/UCO5QFikTtYsQXLa1keonzLw?view_as=subscriber)
