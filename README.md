# Neo4j Configuration

## Download Neo4j

_Neo4j requires java to run_
1. [Download](https://neo4j.com/download-center/#releases) Neo4j Server
2. Extract the content of the folder 
3. Open command prompt (cmd) as administrator 
4. Navigate to _/neo4j-community-3.4.7/bin_
5. Install the bash file with the following command `neo4j.bat install-service`
6. Start Neo4j `net start neo4j`
7. Navigate to [localhost:7474](http://localhost:7474)
8. Check connection with the following cyher command `:server connect`
9. Enter username and password if prompted (neo4j/root)

__Start and Stop Neo4j__
```
net start neo4j
net stop neo4j
```


## Download APOC Plugin
_This library helps with data integration, data conversion and graph algorithms_
1. [Download](https://github.com/neo4j-contrib/neo4j-apoc-procedures/releases) APOC Plugin jar file 
2. Place the APOC plugin jar file in _/neo4j-community-3.4.7/plugin_
3. Configure the Neo4j Config file located in _/neo-community-3.4.7/conf_
4. Add the following lines of code and save the file
```
dbms.security.procedures.unrestricted=apoc.*
apoc.import.file.enabled=true
```


## Select Database
_Selecting specifig graph database to be loaded in Neo4j_
1. Copy the desired graph database folder _example.graphdb_
2. Place the folder in _/neo4j-community-3.4.7/data/databases_
3. Configure the Neo4j Config file located in _/neo-community-3.4.7/conf_
4. Uncomment the following line of code `dbms.active_database=graph.db` _line 9_
5. Change the name of the database to `dbms.active_databases=example.graphdb`
6. Uncomment the following line of code `dbms.allow_upgrade=true` _line 29_





