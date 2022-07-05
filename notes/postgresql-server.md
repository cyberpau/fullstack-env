# PostgreSQL Server

- Install:
```
sudo yum install -y postgresql-server posgresql-contrib
postgresql-setup initdb
```

- Connecting to PostgreSQL Server: `psql -U postgres -p 5432 -h hostname` 

- Create database: `CREATE DATABASE database_name;`

- Create Role or User. Note that Role is NOLOGIN while User is LOGIN: `CREATE <ROLE/USER> backend WITH LOGIN ENCRYPTED PASSWORD 'mysecretpassword';`

- Give permision to role: `ALTER USER role_specification WITH CREATEDB CREATEROLE CREATEUSER;`

- Give privilege to user on database: `GRANT ALL PRIVILEGES ON DATABASE projectraptor TO backend;`

- Common shortcut commands:
    - List all database: `\l`
    - List all tables: `dt`
    - List all database roles: `\du` 
    - Exit `\q`
