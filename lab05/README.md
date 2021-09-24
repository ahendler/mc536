# Aluno
* 231713: Artur Abreu Hendler

## Tarefa de Cypher sobre Marcadores e Taxonomia

## Tarefa 1

Escreva em Cypher uma consulta que retorne os marcadores da categoria `Serviços`, sem considerar as categorias subordinadas.

### Resolução

~~~cypher
match(n)
return (n)-[:Pertence]-(:Categoria{id:"Serviços"})
~~~

## Tarefa 2

Escreva em Cypher uma consulta que retorne os marcadores da categoria `Serviços`, considerando as categorias subordinadas.

### Resolução

~~~cypher
match (c:Categoria{id:"Serviços"})
match (n)-[s:Superior]->(c)
match(n1)
return (n1)-[:Pertence]->(c), (n)-[:Superior]->(c),(n1)-[:Pertence]->(n)
~~~
