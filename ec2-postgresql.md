Set up PostgresSQL database
- `sudo apt install postgresql`
- `sudo systemctl start postgresql.service`
- `sudo -i -u postgres`
- Create a database `createdb {database_name}`
- Change password `ALTER USER postgres PASSWORD '{your_password}';`

Enable remote login
- Go to  /etc/postgresql/<version>/main/postgresql.conf -> `listen_addresses = '*'`
- In pg_hba.conf, add `host    all             all             0.0.0.0/0            md5`
- `sudo service postgresql restart`

--------
For Amazon Linux 2
- `sudo dnf update`
- `sudo dnf install postgresql15.x86_64 postgresql15-server -y`
- `sudo postgresql-setup --initdb`
