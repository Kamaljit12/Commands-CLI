# Cassandra importandt cql

# create keyspaces

    CREATE KEYSPACE tutorialspoint
    WITH REPLICATION = { 'class' : 'SimpleStrategy', 'replication_factor' : 3 };
    
    # or 
    
    CREATE KEYSPACE test
    WITH REPLICATION = { 'class' : 'NetworkTopologyStrategy', 'datacenter1' : 3, 'datacenter2' : 2 }
    AND DURABLE_WRITES = false;

# create table

    CREATE TABLE employee (
      emp_id int PRIMARY KEY,
      emp_name text,
      emp_city text,
      emp_sal varint
    );

# insert data into table

    INSERT INTO employee (emp_id, emp_name, emp_city, emp_sal)
    VALUES (101, 'Alice', 'New York', 50000);

# load data into cassandra table from local computer

    cqlsh:test> copy test.movie 
    (movieid, genres, title) 
    from 'c:\users\kamal\desktop\dataload\movies.csv' 
    with header=true;

    # or

    COPY school.student (id, name, age, grade)
    FROM 'student.csv'
    WITH HEADER = TRUE;

    # or 

    COPY school.student (id, name, age, grade)
    FROM 'student.csv'
    WITH HEADER = TRUE
    AND DELIMITER = '|';



























