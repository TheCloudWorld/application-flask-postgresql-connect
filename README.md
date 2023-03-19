```javascript
from flask import Flask, jsonify
import psycopg2

app = Flask(__name__)

# Database configuration
DB_HOST = "database.cmhr24hwv03d.ap-south-1.rds.amazonaws.com"
DB_PORT = "5432"
DB_NAME = "myapp"
DB_USER = "postgres"
DB_PASSWORD = "Password.725"

@app.route("/")
def index():
    # Connect to the database
    conn = psycopg2.connect(
        host=DB_HOST,
        port=DB_PORT,
        dbname=DB_NAME,
        user=DB_USER,
        password=DB_PASSWORD
    )

    # Create a cursor object
    cur = conn.cursor()

    # Execute a query
    cur.execute("SELECT * FROM myapp")

    # Fetch the results
    results = cur.fetchall()

    # Close the cursor and connection
    cur.close()
    conn.close()

    # Return the results as JSON
    return jsonify(results)

if __name__ == "__main__":
    app.run(host='0.0.0.0', port=3000, debug=True)
'''

## All tools install

sudo yum update
sudo yum install python3 python3-pip nginx
sudo pip3 install flask gunicorn
sudo pip3 install psycopg2-binary


#  
## postgresql client tool install

sudo yum install postgresql -y

## postgresql RDS connect

psql -h <host> -p <port> -U <username> -d <database>

## Create table query

## Query to add the data into the table

INSERT INTO myapp(name, topic)
VALUES ('wilshan', 'devops');
