tags: [[sql]], [[Cursos]]

# Seção 4 - SQL

## 17. Informações dentro de uma tabela

Uma tabela é formada por columns(atribute) e linhas(rows/tupples) e na intersecção entre colunas e linhas armazenam datavalues, que são os dados do banco de dados.
## 18. Tabelas relacionais e Keys
As tabelas tem relações entre elas. E essas relações são formadas pelas keys

**Primary Key:** normalmente é a primeira coluna e é alto incrementada
**Foreign Key:** chaves chamadas de outras tabelas, normalmente são as primary key da tabela origem
## 19. Utilizando USE e SELECT
O comando ```USE``` é utilizado para definir em qual banco de dados será realizada a query.
O comando ``SELECT`` é utilizado para selecionar quais consultas queremos trazer da nossa tabela, e é utilizando junto com o ``FROM`` para especificar de qual tabela vamos trazer as consultas. 
## 20. Ordenando com o ORDER BY
Sempre encerrar os blocos de consulta com o ``;`` 
ORDER BY é usado para ordenar o resultado da query (para str/varchar é ordenado em ordem alfabética).
## 21. Adicionando WHERE e comentando uma linha
```WHERE``` passa uma condição para a query para trazer apenas os dados que cumprem a condição
``--`` é usando para comentar linhas da query
## 22. Modificando Coluna
use ``as`` para definir um alias para as colunas da consulta.
## 25. Operador IN
Podemos passar uma lista de valores no operador ``WHERE`` para ele comparar se esses valores estão na lista usando o operador ``IN``
```
USE SAKILA;

SELECT *
FROM address
WHERE district IN ('Alberta', 'Texas', 'California')
```
## 26. Operador BETWEEN
Usado para verificar se os valores estão entre dois valores.
## 27. Operador LIKE
é usado em consultas para realizar buscas por padrões em colunas de texto (strings). Ele permite encontrar valores que correspondem parcialmente ao padrão especificado.
Podemos usar ele com silabas juntando com % antes ou depois da silaba.
A correspondência com padrão LIKE sempre abrange toda a cadeia de caracteres. Para haver correspondência com o padrão em qualquer posição da cadeia de caracteres, o padrão deve começar e terminar pelo caractere percentagem.

Para corresponder ao próprio caractere sublinhado ou percentagem, sem corresponder a outros caracteres, estes caracteres devem ser precedidos pelo caractere de escape no _padrão_. O caractere de escape padrão é a contrabarra, mas pode ser definido um outro caractere através da cláusula ESCAPE. Para corresponder ao próprio caractere de escape, devem ser escritos dois caracteres de escape.

Deve ser observado que a contrabarra também possui significado especial nos literais cadeias de caracteres e, portanto, para escrever em uma constante um padrão contendo uma contrabarra devem ser escritas duas contrabarras no comando SQL. Assim sendo, para escrever um padrão que corresponda ao literal contrabarra é necessário escrever quatro contrabarras no comando, o que pode ser evitado escolhendo um caractere de escape diferente na cláusula ESCAPE; assim a contrabarra deixa de ser um caractere especial para o LIKE (Mas continua sendo especial para o analisador de literais cadeias de caracteres e, por isso, continuam sendo necessárias duas contrabarras).
## 31. Operador REGEXP
O operador `REGEXP` (ou `RLIKE`, em alguns sistemas como o MySQL) é utilizado em consultas SQL para buscar padrões mais complexos em uma string, usando expressões regulares. Ele oferece mais flexibilidade e poder do que o operador `LIKE`, permitindo buscar correspondências com padrões muito mais específicos.

### Principais Características do `REGEXP`

- **Expressões Regulares**: O `REGEXP` utiliza expressões regulares, que são padrões avançados para combinar texto, com metacaracteres e regras adicionais.
- **Mais Poderoso que LIKE**: Enquanto `LIKE` usa apenas dois curingas (`%` e `_`), o `REGEXP` pode usar uma grande variedade de padrões, como quantificadores (`*`, `+`, `{n}`), listas de caracteres, âncoras (`^`, `$`), entre outros.
- **Buscar uma string que começa com um determinado padrão**: Usando o símbolo `^` para indicar o início da string:
```
SELECT * FROM clientes WHERE nome REGEXP '^Ana';
```
- **Buscar uma string que termina com um determinado padrão**: Usando o símbolo `$` para indicar o final da string:
```
SELECT * FROM clientes WHERE nome REGEXP 'son$';
```
---
# Seção 5 - JOIN

## 35. INNER JOIN
Coloca dados de duas tabelas em uma só, junta duas tabelas.
```
SELECT *
FROM customer
JOIN payment ON customer.customer_id = paymente.payment_id --on é utilizado para indicar as chaves
```
## 39. Operador UNION
Combina os resultados de duas ou mais queries em um único result set, retornando todas as linhas pertencentes a todas as queries envolvidas na execução. Para utilizar o UNION, o número e a ordem das colunas precisam ser idênticos em todas as queries e os data types precisam ser compatíveis.
O operador UNION, por default, executa o equivalente a um SELECT DISTINCT no result set final. Ele elimina as duplicatas automaticamente. Este processo é executado mesmo que não hajam registros duplicados.

---

# Seção 6 - Manipulando dados

40. Informações sobre tabelas

	No mysql workbench podemos verificar as informações da tabela e verificar tipos de dados nas linhas e também os parâmetro (not null, primary key, foreign key, auto increment).
	
	Podemos também selecionar os dados default para as linhas quando houver uma nova inserção
	
41. Adicionando uma linha na tabela
	
	Utilizamos a seguinte sintaxe para inserir dados em uma tabela:
```
INSERT INTO nome_tabela (podemos inserir as colunas que iremos inserir os dados)
VALUES (inserimos os valores)
```
	
42. Adicionando multiplas linhas
	
	Para isso precisamos apenas inserir mais linhas de valores no código acima.
	
	Para inserir em várias tabelas, basta fazer o código acima para todas as tabelas que deseja.
	
44. Copiar uma tabela completa
	vamos fazer o comando de inserir uma tabela juntamente com um select da tabela que 
	desejamos copiar.
	
45. Remover uma tabela
	DROP TABLE remove os dados e a tabela do meu schema
	TRUNCATE TABLE remove apenas os dados da minha tabela, mantendo a mesma no schema.
	
46. Atualizando um valor
	Usamos o comando UPDATE e com o SET para definir qual vai ser o valor atualizado, juntamente com o WHERE para definir qual vai ser o registro que será alterado.
---
# Seção 7 - Funções
48. Introdução a Funções
	[Funções](https://www.w3schools.com/sql/sql_ref_sqlserver.asp)
49. Funções básicas
	max() pega o valor máximo de uma coluna
	min() pega o valor minimo de uma coluna
	avg() pega a média de valores de uma coluna
	Podemos usar ``as`` para definir nomes
50. Utilizando COUNT e SUM
	SUM() soma a todos os valores de uma coluna
	COUNT() conta valores not null de uma coluna