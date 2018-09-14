# APOC Plugin

## Calling procedures and functions within Cypher

__Load Local JSON file__
```python
CALL apoc.load.json("file:/Users/mustafa.hakimi/desktop/jsondata/cleveland/virkdata/user_virk.json") yield VALUE as user
MERGE (u:User {user_id: user.user_id})
SET u.name = user.name,
    u.age = user.age
```