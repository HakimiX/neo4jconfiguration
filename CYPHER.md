# Neo4j Cypher

Neo4j uses a declarative, SQL-inspired language for describing patterns in graphs visually.
It allows us to state what we want to select, insert, update og delete from our graph data. 
The following cypher query creates nodes and relationships. 

```javascript
CREATE (virk1:Virksomhed {cvr:'15459778', navn:'Sørensen og Jørgensen ApS', branchekode:'702040'})
CREATE (virk2:Virksomhed {cvr:'25977458', navn:'Martin og Olsen ApS', branchekode:'702040'})

CREATE (p1:Person {navn:'Jørn Mikkelsen Schmidt', hovedtype:'REVISION'})
CREATE (p2:Person {navn:'Arne Ellgård Hansen', hovedtype:'LEDELSESORGAN'})
CREATE (p3:Person {navn:'Mogens Møller Sørensen', hovedtype:'STIFTERE'})

CREATE
(p1)-[:CONNECTED_TO {roles:['REVISION']}]->(virk1),
(p2)-[:CONNECTED_TO {roles:['LEDELSESORGAN']}]->(virk1),
(p3)-[:CONNECTED_TO {roles:['STIFTERE']}]->(virk1)

CREATE (p4:Person {navn:'Anders Mogensen', hovedtype:'REVISION'})
CREATE (p5:Person {navn:'Arne bensen', hovedtype:'LEDELSESORGAN'})
CREATE (p6:Person {navn:'Bølle Sørensen', hovedtype:'STIFTERE'})

CREATE
(p4)-[:CONNECTED_TO {roles:['REVISION']}]->(virk2),
(p5)-[:CONNECTED_TO {roles:['LEDELSESORGAN']}]->(virk2),
(p6)-[:CONNECTED_TO {roles:['STIFTERE']}]->(virk2),
(p1)-[:CONNECTED_TO {roles:['REVISION']}]->(virk2),
(p2)-[:CONNECTED_TO {roles:['REVISION']}]->(virk2)

CREATE
(virk1)-[:CONNECTED_TO {roles:['Datterselskab']}]->(virk2)
```

![text](https://github.com/HakimiX/neo4jconfiguration/blob/master/Images/virksomhedGraph.png)