## Flask Web Application to fetch data from Postgresql database


## Tools needs to be installed on Web Server

```bash
sudo yum update -y
sudo yum install python3 python3-pip nginx -y
sudo pip3 install flask gunicorn -y
sudo pip3 install psycopg2-binary -y
```

## Bastion Host - Postgresql client tool install

```bash
sudo yum install postgresql -y
```

## postgresql RDS connect
```bash
psql -h <host> -p <port> -U <username> -d <database>
```

## Create table query

## Query to add the data into the table
```bash
INSERT INTO myapp(name, topic)
VALUES ('wilshan', 'devops');
```
