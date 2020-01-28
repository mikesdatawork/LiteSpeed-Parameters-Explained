![MIKES DATA WORK GIT REPO](https://raw.githubusercontent.com/mikesdatawork/images/master/git_mikes_data_work_banner_01.png "Mikes Data Work")        

# LiteSpeed Parameters Explained
**Post Date: April 14, 2014**        



## Contents    
- [About Process](##About-Process)    
- [Build Info](#Build-Info)  
- [Author](#Author)  
- [License](#License)       

## About-Process

<p>It seems since the acquisition of LiteSpeed again and again has somewhat fragmented the amount of available information, so I'll post up what I have in my notes about the LiteSpeed Parameters.
LiteSpeed Parameters explained.
LiteSpeed provides a number of different backup options which are set in the LiteSpeed Defaults but may be changed for individual backup and restore jobs.
Resolution
Some of the options discussed below are advanced options and should only be changed if there is a thorough understanding of the affects the changes.
Affinity
In Windows this is a number which specifies the number of processors that will be used by the running process. Use this to increase performance on multi-processor machines, when operating under heavy loads. Leaving this to 0 (default) provides the best performance in most cases. This is an advanced option, do not alter this setting without referring to the LiteSpeed Help File or SQL Server Books Online by searching for 'affinity' for a complete explanation of the function.
Backup Threads
This is the number of simultaneous processes to use to create the backup. This is used on Multi-Processor environments where the backup job is split over a number of different processes to create the backup file. Large databases tend to be backed up faster when the job load is spread over a number of processes. Each process creates a separate backup file which LiteSpeed interleaves as one backup file. However, if the native files were extracted using the Extractor Utility provided by LiteSpeed, the number of files created is the same as the number set for Threads. These files will need to be restored together, as a set, using SQL Server native restore commands as a striped backup.
Encryption Level
Level of Encryption required. A password will need to be entered to allow the file to be decrypted. There are currently 9 levels of encryption available. The greater the encryption level, the longer it will take to perform the backup/restore.
Compression Level
The level of compression required for the backup. The greater the level of compression the longer it will take to backup/restore a file. The default value is 1 and the max value is 11. A value of 0, bypasses the compression routines; therefore, there is no difference between the Native and LiteSpeed backup file sizes.
Priority
CPU Priority is a setting that adjusts the amount of CPU cycles that the background and foreground applications receive. The default is Normal. Changing this Setting will take up more CPU usage while the backup process is running. Valid options are: 0 Normal (Default), 1 AboveNormal , 2 High Note: This parameter is not available for the restore process, only backup
Max Transfer Size
This is the size of the chunks of data that are sent togethyer over to the backup device. These can be changed if slow performance is being experiencing when backing up databases. This should not be set to a value more than 4Mb (4194304 bytes) as this is the limit and it should not be set below 64Kb (65536 bytes). The default is 1Mb (1048576 bytes).
Buffer Count
Microsoft recommendations for working out the buffer count is to use the formula below:
NumberofBackupDevices*3 + NumberofBackupDevices + NumberofDatabaseFiles = BufferCount
In LiteSpeed, the maximum value for the buffer count is 150. The buffer count should be set to a number that is greater than the number of backup devices. The LiteSpeed default is 20. Again this can be changed if performance issues are being experienced with the backup. You can use the BufferCount parameter to change the number of memory blocks that are the size as specified by the MaxTransferSize parameter and that are fetched by the read ahead feature at one instance.
Throttle
This sets the maximum CPU usage allowed for the backup process as a percentage. The default is 100%.
There are also a number of other parameters that can be used, which currently are not documented, but you'll have to look for those. These are the most common.</p>


[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Author

[![Gist](https://img.shields.io/badge/Gist-MikesDataWork-<COLOR>.svg)](https://gist.github.com/mikesdatawork)
[![Twitter](https://img.shields.io/badge/Twitter-MikesDataWork-<COLOR>.svg)](https://twitter.com/mikesdatawork)
[![Wordpress](https://img.shields.io/badge/Wordpress-MikesDataWork-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

   
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Mikes Data Work](https://raw.githubusercontent.com/mikesdatawork/images/master/git_mikes_data_work_banner_02.png "Mikes Data Work")

