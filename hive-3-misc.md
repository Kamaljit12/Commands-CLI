# To create database
    $ create database temp_db; 

    $ show database;
# To see the database under which working
    $ set hive.cli.print.current.db=true;

# create table
    $ create table hive_test(id int, name sting, salary int, city string)
    row format delimited fileds terminated by ','
    tblproperties("skip.header.line.count"="1");
    # To describe hive table
    > describe formatted hive_test;
    
# laod data from edge node(local file system)
    $ load data local inpath '<local source file path>' into table hive_test;

# To see the data with columan name/ header
    $ set hive.cli.print.header=true;

# To oevrwirte data into the table
    $ load data local inapth <local source file path> overwrite into table hive_test;

# load data from hdfs into table
    $ load data inpath '<hdfs file path>' into table hive_test;

# To create a file using vi command
    $ vi file.txt

# To read or view the text of the file
    $ cat file.txt
--- DataType MAP - collection of element which contains key and value-------------

# To create and write text in file
    $ cat > file.txt
    hello
    i am kamal
    i am data enginner
    and i am creating a file using cat cli
Note:
press Enter
press ctrl + D to save the file

# creating a file for map funcion
    $ cat > array_map.txt
    id, name, sal, lappy_info, pf_info, city
    1, kamal, 40000, laptop$mouse$bag$extended monitor$ph, df#500$epf#200, pune
    2, durga, 3000, laptop$mouse$bag$ph, pf#500, hyd
    3, chanda, 40000, desktop$mouse$car$extended monitor$ph, pf#500$epf#200, hyd
    4, somil, 3000, laptop$mouse$bag$extended monitor$ph, pf#500$epf#300$ppf#686, pune



# Create table for map function in hive
    create table array_map(id int, name string, sal int, lappy arry<string>, df_info map<string, int>, city string)
    row format delimited fields terminated by ','
    collection items terminated by '$'
    map keys terminated by '#'
    tblproperties("skip.header.line.count"="1")

# hive query
    > select pf_info["pf"] from array_map;
    > select pf_info["epf"] from array_map;
    > select lappy_info[1] # selecting values using indexing
    
2.>>>>>>>>>>>>>>>>>>>>>>
---- DataType STRUCT - it's a cllection of different elements of different DataTypes---------------

# text file
    id, name, sal, subject, deducation, address
    1, kamal, 2000, hadoop$spark$scala, pf#500$epf#20, mh$pune$421302
    2, chanda, 5000, python$java$c++,c#, epf#500, BR$Ara$802165

# create table
    > craete table array_struct(id int, name string, sal int, subject array<string>, deducation map<string, int>, address string)
    row format delimited 
    fields terminated by ','
    collection items terminated by '$'
    map keys terminated by '#'
    tblproperties("skip.header.line.count"="1")

# hive query 
    > select address.col1 from array_struct;


