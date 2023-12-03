# To create empty file
    hadoop fs -tocuhz fileName.txt

# To copy file from hdfs to local
     hadoop fs -get <source hdfs file location> <destination local file location>

# Copy file from hdfs to local
    hadoop fs -copyToLocal <hdfs source location> <destination local file location>

# Copy file form local to hdfs
    hadoop fs -copyFromLocal <local source location> <destination hdfs location>

# To append data from local file to hdfs file
    hadoop fs -appendToFile <source file location> <another destionation hdfs file location>

# To read or see or view the file 
    hadoop fs -cat <file path>

# To remove file from hdfs 
    hadoop fs -rm <file path>

# To count file 
     hadoop fs -usage count
     hadoop fs -count -q <hdfs file path>
     hadoop fs -count -q -h <hdfs file path>
     hadoop fs -count -q -h -v <hdfs file path>

# To see the file details
    hadoop fs -du -h <hdfs file path>
    hadoop fs -df -h <hdfs file path>

# Some Important
    user:group:others <---:---:--->
    -rw-r--r--
    file:
    -rwxr--r--

    drw-r--r--

    chmod:
    read --> r --> 4
    write --> w --> 2
    execute --> x --> 1

    chmode u+777

    Some commands

    chmod u+x <file name>
    chmod 644 <file name> 
    chmod 777 <file name>
    chmod g-x, o-x <file name>

# stats command
    hadoop fs -stat %u <hdfs file path>
    hadoop fs -stat %n <hdfs file path>
    hadoop fs -stat %b <hdfs file path>
    hadoop fs -stat %r <hdfs file path>
    # To check the replicaion
    hadoop fs -stat %r %n <hdfs file path>
    hadoop fs -stat %r, %n <hdfs file path>

# To see last 20 rows 
    hadoop fs -tail <hdfs file path>
# To see file 20 rows
    hadoop fs -head <hdfs file path>

# Use help command to get help of the command
    hadoop fs -usage test
    # or 
    hadoop fs -help test

# test command
    hadoop fs -test -d <hdfs file path>\
    echo $?
    hadoop fs -test -f <hdfs file path>
    echo $?
    hadoop fs -test -e <hdfs file path>
    echo $?
    hadoop fs -test -s <hdfs file path>
    echo $?
    hadoop fs -test -z <hdfs file path>
    echo $?

# To set replication
    # Here 3 is the replication factor 
    hadoop fs -setrep 3 <hdfs file path>
    # To check the replication
    hadoop fs -stat %r <hdfs file path>
# To find the file in particular location
    hadoop fs -find <hdfs file location> -name <file name>
    # Example:
    hadoop fs -find /user/dfs/ -name file.txt

# This is unknow command please try and check it
    hadoop fs -getfacl <hdfs file location>
    hadoop fs -getfacl -R <hdfs file location>
    
    
