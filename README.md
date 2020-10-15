# neo4j_practice at het.io
1. Collect Symptoms for each of the disease
```
MATCH (d:Disease)--(s:Symptom) RETURN d.name,collect(s.name)
```
2. Know schema of the graph data
```
CALL db.schema()
```

<img src="grph.png" width="400px" height="400px"></img>
