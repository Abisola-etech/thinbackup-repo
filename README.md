# thinbackup-repo,what is the use of a thinbackup plugin and how it is used to perform backup configurations


 thinBackup plugin is used to configure backup of a jenkins server to recover critical
   configurations files in case the jenkins server crashes
   and also this configs can be extended with nfs server for strong backups
   
   we have used it to back up some jobs on our jenkins by configuring a cronjob should the jenkins server crashes by :
   
   On our jenkins UI,installing the thinbackup plugin on our jenkins server and clicking on the settings
   then go to the CLI (backend)  (and making sure Ubuntu is the user)to create a directory
   by running a command : sudo mkdir -p /team3/grp2-backup
    sudo chown jenkins:jenkins /team3/grp2-backup.
    
    we go back to the jenkins UI and continue with the configuration by adding the directory we created ( /team3/grp2-backup)
    then configure a cronjob which will run at 2pm, every mondays to fridays ( H 14**1-5)  and also backup schedule for differential backup then 
    selecting number of backup set and files to be excluded like the .log files
    then we untick the wait until Jenkins is idle and moved to build result by choosing 'backup build archive' backup 'userContent' folderBackup next build number file
    Backup plugins archives and also Move old backups to ZIP files. we then save.
     We clicked the 'Backup now' and went to the CLI to list what we have by using the ls command and it showed the the FULL date and time it was backed up
     
