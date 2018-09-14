# APOC Plugin

## Calling procedures and functions within Cypher

The APOC library consists of procedures and functions to help with data integration, graph algorithms and data conversion

__Load Local JSON file__
```javascript
CALL apoc.load.json("file:/Users/mustafa.hakimi/desktop/jsondata/example.json") 
yield VALUE as user
MERGE (u:User {user_id: user.user_id})
    SET u.name = user.name,
        u.age = user.age
```

__Load JSON file from web__
```javascript
WITH 'https://example.com/jsondata/person.json' AS url
CALL apoc.load.json(url) YIELD value as user
MERGE (u:User {name:user.name})
   ON CREATE SET u.age = user.age
```

