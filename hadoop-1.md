# Commands is for all operating system

## start hadoop in  in windows
- start.dfs.cmd or
- start.all.cmd,
- start-yarn.cmd

# check directory in hadoop
    $ hadoop fs -ls /

# create directory in hadoop
    $ hadoop fs -mkdir dirName

# create a empty file
    $ hadoop fs -touchz file.txt

# create a file in local system
### Note: f1.txt will be created in local system so edit this file and wrote something in this file.
    $ gedit f1.txt

# copy file from local to hdfs
### Note: Here f1.txt is the file name and dirName is the directory name where file is coppying
    $ hadoop fs -copyFromLocal f1.txt dirName

# display the file from hdfs
    $ hadoop fs -cat dirName/f1.txt

# copy file from hdfs to local disk
### Note: I am copying this file to hdfs to local disk on the desktop location
    $ hadoop fs -copyToLocal newDir/f1.txt ~/Desktop/

# copy file from one directory to another directory
### Note: Copyin file from newdir1 to newDir2 these both are directoy present in hdfs file system
    $ hadoop fs -cp newDie1/f1.xtx /newDir2

# move file from one directory to another directory
    $ hadoop fs -mv newDir1/f1.xtx /newDir2

# check the file size
### Note: It will show the size of each file of the directory
    $ hadoop fs -du newDir1

# check the total directory size
### Note: It will show the total size of the directory
    $ hadoop fs -dus newDir1

# test command
    $ hadoop fs -test -d dirName
#### To verify the command and -d represents to directory
    $ echo $?

    $ hadoop fs -test -e dirName
#### To verify the command and -e represents to existance of directory
    $ echo $?
    $hadoop fs -test -f dirName
#### To verify the command and -d represents to file
    $ echo $?
    $ hadoop fs -test -z dirName
#### To verify the command and -d represents to zero content directory
    $ echo $?

# move from local 
    $ hadoop fs -moveFromLocal file.txt dirName/

# merger two file
#### Note: Here -nl represents to new line 
  $ hadoop fs -getmerge -nl fiel1.txt file2.txt

# append data from another files
#### Here i am trying to append file1.txt and file2.txt in file3.txt
    $ hadoop fs -appenToFile file1.txt file2.txt file3.txt

# To check what activity and actions has happen in the dir or file
    $ hadoop fs -checksum dirName/file.txt

# file system status check 
    $ hadoop fsck - /

# To know total file size
    $ hadoop fs -count dirName/

# To remove file from directory
    $ hadoop fs -rm dirName/file.txt

# To change the group name
#### Note: here kamal is the new group name of the file.txt group
    $ hadoop fs -chgrp kamal dirNmae/file.txt

# To check the status
## -stat command 
#### Note: here %b represents to total file size in bites
    $ hadoop fs -stat %b dirName/file.txt

  #### Note: here %b represents to group name of the file
    $ hadoop fs -stat %g dirName/file.txt
  
  #### Note: here %r represents the replication factor of the file
    $ hadoop fs -stat %b dirName/file.txt
  
  #### Note: here %y represents to show the status when the file got modified
    $ hadoop fs -stat %b dirName/file.txt



