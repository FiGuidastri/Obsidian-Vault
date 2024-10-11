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
