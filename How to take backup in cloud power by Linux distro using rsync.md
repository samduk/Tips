### How to take backup in cloud power by Linux distro using rsync

- Command to take backup on Linux Machine (VPS - Virtual Private Server etc)
  - ```rsync -a source/ destination/```  similar to   ```copy source/ destination/```

#### Side dish

     - How to zip the file on Linux
      - ```tar -czvfp file.tar.gz sourcefolder```
      - - c compress
      - - z (protocol suchas gzip, gunzip, ungunzip etc)
      - - v verbose
      - - f regular file (or just file)
      - - p preserver permission (However, on some linux distro it doesn't work)

    - How to unzip file on Linux
      - ```tar -xzvfp file.tar.gz```
      - - x extract

### Main course (lol)

- Command to take backup and send the backup to a remote machine    
  - ```rsync -a -e ssh source/ user@remoteip.com:/path/to/destination```
  - Remmember: It is important to take a hash of your backup file
    - ```shasum -a 256 file.tar.gz```   And keep the value somewhere safe
- To update your backup folder with new changes    
  - ```rsync -a --delete source-folder  destination-folder```


### Video Tutorial in Tibetan (Dessert ;))
  - [Youtube](https://youtu.be/oGu-yFycZPc
)
