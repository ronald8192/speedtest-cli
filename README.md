# speedtest-cli with MySQL#
---
This version of `speedtest-cli` added save result to MySQL server function.

Use `--save` to use this feature.

## MySQLdb module ##
This program use the MySQLdb module to access MySQL database.
Install MySQLdb in Ubuntu:
```
$ sudo apt-get install python-mysql
# or
$ sudo pip install MySQL-python
```

## Configuration ##
Database address, username and password can be configure by setting the environment variable: 
 * `speedtest_db_host` : database host
 * `speedtest_db_user` : database username
 * `speedtest_db_password` : database password

Configure in `~/.bashrc`:
```
export speedtest_db_host="127.0.0.1"
export speedtest_db_user="db_username"
export speedtest_db_password="db_password"
```

## Database ##
The test data will save into `speedtest` database's `speedtest` table.

### Attributes ###
* `id`: Primary key
* `ping`: Ping in ms
* `down`: Download speed (Mbps)
* `up`: Upload speed (Mbps)
* `server`: Speedtest.net server ID
* `ref`:  Result image ID (only available when `--share` option is used)
* `create_at`: Record create time