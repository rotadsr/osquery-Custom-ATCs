# osquery-Custom-ATCs
Custom ATC's ready for being used in OSquery

Usage:
```sh
sudo /usr/local/bin/osqueryi --config_path PATH_TO_THE_FILE.json
```
> This will load OSquery with the config ATCs present in the configuration file.

Contributing:
* Install `sqlite3` in your system or use any other DB browser such as [DB Browser for SQLite](https://sqlitebrowser.org).
* Basic sqlite3 knowledge would be beneficial, but not required if you follow the next steps:
  *   Opening a DB file: `sqlite3 full_path_to_the_table`
  *   List all the tables once in the SQLite3 console: `.tables`
  *   Extract table headers once in the SQLite3 console: `SELECT * FROM sqlite_master WHERE name='TABLE_NAME';`
  *   Exit SQLite3 console `.exit`
* Use the following syntax schema for creating your ATC:
```json
{
    "auto_table_construction" : {
        "DBfilename_tablename" : {
            "platform": "darwin|windows|ubuntu|centos",
            "query": "SELECT * FROM tablename",
            "path" : "PATH_TO_THE_DB_FILE",
            "columns" : [
              "column1",
              "column2",
              "column_n"
            ]
        }
    }
}
```
* Verify it's working locally before creating a PR.
* Create a new branch adding the JSON file and a brief explanation on what's the usage.
    * You must add the table headers from `sqlite3` and the relative full path of the database file.
    * You must create separate files for each different platform and PR all of them in their respective folder.
  
