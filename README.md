# Neo4J practice at ```het.io```

Open https://neo4j.het.io/browser/ and practise following cypher queries:

1. Collect Symptoms for each of the disease
```
MATCH (d:Disease)--(s:Symptom) RETURN d.name,collect(s.name)
```
2. Know schema of the graph data
```
CALL db.schema()
```

<img src="graph.png" width="300" height="300"></img>

3. Collect genes associated with each of the disease
```
MATCH (d:Disease)--(g:Gene) RETURN d.name,collect(g.name)
```
4. Count gene and pathways for each diseases
```
MATCH (d:Disease)--(g:Gene)--(p:Pathway) RETURN d.name,count(g.name),count(p.name)
```
5. Count and collect associated compound with disease
```
MATCH (d:Disease)--(c:Compound)--(s:SideEffect) 
RETURN d.name,count(DISTINCT c.name),collect(DISTINCT c.name)
```
6. Visualize a subgraph of associated compound with disease and side effects (100 nodes)

```
MATCH p=(d:Disease)--(c:Compound)--(s:SideEffect) RETURN p LIMIT 100
```

<img src="graph-2.png" width="300" height="300"></img>

7. Visualize the subgraph of Disease, Gene and Pathways (100 nodes)

```
MATCH path=(d:Disease)--(g:Gene)--(p:Pathway) RETURN path LIMIT 100
```
<img src="graph-1.png" width="300" height="300"></img>

