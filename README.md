# neo4j_practice at het.io
1. Collect Symptoms for each of the disease
```
MATCH (d:Disease)--(s:Symptom) RETURN d.name,collect(s.name)
```
2. Know schema of the graph data
```
CALL db.schema()
```

<img src="graph.png" width="400" height="400"></img>
