# 🐘 PostgreSQL Daily Use Commands

## ✅ Set/Reset PostgreSQL Password (Linux)

```bash
# Login to psql
sudo -u postgres psql

# Inside psql, run:
ALTER USER postgres WITH PASSWORD 'password';
✅ Connect to PostgreSQL
bash
Copy code
sudo -u postgres psql                      # Login as 'postgres' user (Linux)
psql -U username -d dbname                 # Login with specific user and database
psql                                       # Connect to default DB as current user
Exit psql: \q

📁 Database Commands
sql
Copy code
\l                             -- List all databases
CREATE DATABASE mydb;          -- Create a new database
DROP DATABASE mydb;            -- Delete a database
\c mydb                        -- Connect to a database
👤 User / Role Management
sql
Copy code
\du                                         -- List all roles/users
CREATE USER john WITH PASSWORD '123';       -- Create a new user
ALTER USER john WITH SUPERUSER;             -- Grant superuser
DROP USER john;                             -- Delete user

-- Grant access to a database
GRANT ALL PRIVILEGES ON DATABASE mydb TO john;
🧱 Table Commands
sql
Copy code
\d                   -- List all tables
\d tablename         -- Describe a table
CREATE TABLE ...     -- Create a new table
DROP TABLE ...       -- Delete a table
Example:
sql
Copy code
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name TEXT NOT NULL,
  email TEXT UNIQUE
);
📊 CRUD Operations
INSERT
sql
Copy code
INSERT INTO users (name, email) VALUES ('Alice', 'alice@example.com');
SELECT
sql
Copy code
SELECT * FROM users;
SELECT name FROM users WHERE id = 1;
UPDATE
sql
Copy code
UPDATE users SET email = 'new@example.com' WHERE id = 1;
DELETE
sql
Copy code
DELETE FROM users WHERE id = 1;
🧠 Indexes & Constraints
sql
Copy code
CREATE INDEX idx_email ON users(email);
ALTER TABLE users ADD CONSTRAINT email_unique UNIQUE(email);
📂 Import / Export Data
Export table to CSV
sql
Copy code
\COPY users TO 'users.csv' WITH CSV HEADER;
Import CSV into table
sql
Copy code
\COPY users FROM 'users.csv' WITH CSV HEADER;
🛠️ Admin & Maintenance
sql
Copy code
\conninfo                     -- Show current connection info
SELECT version();             -- Show PostgreSQL version
SELECT current_database();    -- Get current database
🧹 Cleanup & Utilities
sql
Copy code
TRUNCATE TABLE tablename;     -- Empty a table (fast delete)
VACUUM;                       -- Clean up and reclaim space
ANALYZE;                      -- Update planner stats
🐚 System Commands (Linux CLI)
bash
Copy code
createdb mydb                 # Create a database
dropdb mydb                   # Drop a database
createuser myuser             # Create a user
dropuser myuser               # Delete a user
🔐 Reset Password (psql)
sql
Copy code
ALTER USER postgres WITH PASSWORD 'newpassword';
🧾 Bonus: Useful psql Meta-Commands
Command	Description
\l	List all databases
\c dbname	Connect to a database
\dt	List all tables
\d tablename	Describe table structure
\du	List all users/roles
\conninfo	Show connection info
\q	Quit psql
