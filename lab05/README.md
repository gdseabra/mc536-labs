# Lab05 - Marcadores e Taxonomia em Cypher

Estrutura de pastas:

~~~
├── README.md  <- arquivo apresentando a tarefa
~~~

# Aluno
* 216213: Gabriel Dourado Seabra

## Tarefa de Cypher sobre Marcadores e Taxonomia

## Tarefa 1

Escreva em Cypher uma consulta que retorne os marcadores da categoria `Serviços`, sem considerar as categorias subordinadas.

### Resolução
~~~cypher
MATCH (n:Marcador)-[:Pertence]->(:Categoria {id:"Serviços"})
RETURN m
~~~

## Tarefa 2

Escreva em Cypher uma consulta que retorne os marcadores da categoria `Serviços`, considerando as categorias subordinadas.

### Resolução
~~~cypher
MATCH (m:Marcador)-[:Pertence]->(:Categoria)-[:Superior]->(:Categoria {id:"Serviços"})
MATCH (n:Marcador)-[:Pertence]->(:Categoria {id:"Serviços"}) 
RETURN m,n
~~~
