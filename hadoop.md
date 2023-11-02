# Commands is for all operating system

## start hadoop in  in windows
- start.dfs.cmd or
- start.all.cmd,
- start-yarn.cmd

# check directory in hadoop
hadoop fs -ls /

# create directory in hadoop
hadoop fs -mkdir dirName

# create a empty file
hadoop fs -touchz file.txt

# create a file in local system
### Note: f1.txt will be created in local system so edit this file and wrote something in this file.
$ gedit f1.txt

# copy file from local to hdfs
### Note: Here f1.txt is the file name and dirName is the directory name where file is coppying
hadoop fs -copyFromLocal f1.txt dirName

# display the file from hdfs
hadoop fs -cat dirName/f1.txt

# copy file from hdfs to local disk
### Note: I am copying this file to hdfs to local disk on the desktop location
hadoop fs -copyToLocal newDir/f1.txt ~/Desktop/

# copy file from one directory to another directory
### Note: Copyin file from newdir1 to newDir2 these both are directoy present in hdfs file system
hadoop fs -cp newDie1/f1.xtx /newDir2

# move file from one directory to another directory
hadoop fs -mv newDir1/f1.xtx /newDir2

# check the file size
### Note: It will show the size of each file of the directory
hadoop fs -du newDir1

# check the total directory size
### Note: It will show the total size of the directory
hadoop fs -dus newDir1



