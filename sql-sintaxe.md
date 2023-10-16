## Criando um banco de dados

> CREATE DATABASE nomeBanco;

## Backup do banco de dados

> BACKUP DATABASE nomeBanco TO DISK = 'Caminho a ser salvo'; 

## Criando uma tabela

Ao criar uma tabela especificamos seu nome e o nome das colunas com o tipo de dados que sera inserido na mesma como inteiro, caractere, strings, data etc.

> CREATE TABLE nometabela (   
>   nomeColuna1 VARCHAR(45) NOT NULL, 
>   nomeColuna2 VARCHAR(45) NOT NULL, 
>   nomeColuna...n VARCHAR(45) NOT NULL);

## Apagando uma tabela

> DROP TABLE nomeTabela 

## Adicionando colunas a uma tabela existente

Com esse comando você cria uma nova coluna, especifique também o tipo de dado da coluna como inteiro, varchar, data etc.

> ALTER TABLE nomeTabela ADD nomeColunaNova varchar(255)

## Inserindo dados em uma tabela

> INSERT INTO nomeTabela (nomeColuna1, nomeColuna2, nomeColuna3) VALUES (valorParaColuna1, valorParaColuna2, valorParaColuna3);

## Inserindo dados em uma tabela em forma de dados ou variáveis

Na função abaixo cada ? sera adicionado ao valor da coluna correspondente, geralmente usamos esse metódo para receber dados de uma função.

> INSERT INTO nomeTabela (nomeColuna1, nomeColuna2, nomeColuna3) VALUES (?, ?, ?)

## Deletando dados em uma tabela

> DELETE FROM nomeTabela WHERE nomeColuna = "nome do dado a ser deletado"

## Deletando dados em uma tabela em forma de dados ou variáveis

Na função abaixo iremos passar o id de uma coluna como parâmetro do ?

> DELETE FROM tasks WHERE id = ?, [id]

## Atualizando dados em uma tabela

> UPDATE nomeTabela SET nomeColuna = 'dado a ser alterado' WHERE nomeColunaReferencia = referencia;

## Atualizando dados em uma tabela em forma de dados ou variáveis

> UPDATE tasks SET nomeColuna1 = ?, nomeColuna2 = ? WHERE colunaReferencia = ?,[varValue1, varValue2, varValue3]

## Selecionando todos os itens de uma tabela

Retorna todos os dados de uma tabela

> SELECT * FROM nomeTabela

## Selecionando colunas de uma tabela

Retornar os dados daquela coluna

> SELECT nomeColuna1, nomeColuna...n from nomeTabela

## Selecionando e trocando o nome de uma coluna

Retorna a coluna selecionada com o novo nome

> SELECT nomeColuna1 AS novoNomeColuna1 from nomeTabela

## Selecionando uma coluna e definindo a ordem 

Retorna os dados de uma coluna em crescente ou decrescente para crescente use "ASC"

> SELECT nomeColuna FROM nomeTabela ORDER BY nomeColuna DESC

## Selecionando dados implicitos

Retorna dados de uma coluna de acordo com o parametro where

> SELECT nomeColuna FROM NomeTabela WHERE nomeColuna = "Valor procurado"

## Selecionando dados implicitos com operador "ou"

Retorna os dados que combinam com o parametro where

> SELECT nomeColuna FROM nomeTabela WHERE nomeColuna = "valor  esejado 1" OR nomeColuna = "valor  esejado 2"

## Selecionando dados de uma coluna que contem "algo"

Retornar os dados que contem aqueles conjunto de caracteres desejados conforme a posisao do %

o %valorDesejado no inicio retorna valores que contem o valor desejado apos a primeira letra

> SELECT nomeColuna FROM nomeTabela WHERE nomeColuna LIKE "%a"
- Vai retornar valores que a segunda letra sejam a

O %valorDesejado% entre os % retorna valoes que contem entre o valor desejado

> SELECT title FROM atletas WHERE title LIKE "%e%"
- Vai retornar valores que contem letra e entre o %

## Limitando quantidade de dados selecionandos

Retorna os dados desejados limitando a quantidade a ser mostrada, no exemplo sera mostrado os 3 primeiros resultados da coluna.

> SELECT nomeColuna FROM nomeTabela LIMIT 3

## Retornando a quantidade de dados de uma coluna

Vai retornar quantos elementos tem na coluna

> SELECT DISTINCT COUNT(nomeColuna) FROM nomeTabela

## Concatenando colunas

Retorna os dados da coluna concatenando as dados da coluna1 da virgula e da coluna2

> SELECT nomeColuna, CONCAT(nomeColuna1, ", ", nomeColuna2) FROM nomeTabela

## Condicional CASE

Retorna os dados com base numa condicao ou outra usando o CASE THEN

> SELECT nomeColuna1, nomeColuna2, CASE WHEN nomeColuna2 >=3 THEN 'Mostra se nomeColuna2 tiver itens maior ou igual a 3' 
> WHEN ID <2 THEN 'Mostra se nomeColuna2 tiver itens menor que 2' 
> ELSE 'Mostra os itens que nao se encaixam nas condicioes criadas' 
> END 
> FROM atletas

