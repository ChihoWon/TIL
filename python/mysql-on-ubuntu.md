# What you need

```sh
$ sudo apt-get install python3-dev libmysqlclient-dev
$ pip install mysqlclient
```

# Code

See the example below:  

```python
#-*- coding: utf-8 -*-
import MySQLdb

# information
url = 'dburl'
userid = 'username'
passwd = 'password'
dbname = 'dbname'

# open database connection
db = MySQLdb.connect(url, userid, passwd, dbname, charset='utf8')
db.autocommit(on=True)

# prepare cursor
cursor = db.cursor()

# get version
cursor.execute('select version()')
data = cursor.fetchone()
print(data)

# insert
cursor.execute("insert into pythontable(name) values('Exxiot')")
cursor.execute("insert into pythontable(name) values('Tyrell')")
cursor.execute("insert into pythontable(name) values('Mr. robot')")
cursor.execute("insert into pythontable(name) values('idiot')")
cursor.execute("insert into pythontable(name) values('한국인')")

# update
cursor.execute("update pythontable set name='Elliot' where idx=1")

# delete
cursor.execute("DELETE from pythontable WHERE idx = 4")

# select
cursor.execute("select * from pythontable order by idx DESC")
data = cursor.fetchall()

for record in data:
    print(record)

cursor.close()
```

It is self-explanatory.
