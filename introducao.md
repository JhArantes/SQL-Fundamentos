INTRODUÇÃO

A principal função de um sistema de banco de dados é proporcionar recursos para armazenamento, manutenção e consulta dos dados, de maneira segura e eficaz.

A consulta de dados é uma pesquisa realizada no banco de dados, cujo propósito é recuperar as linhas (registros) que atendem às condições pré-estabelecidas. As consultas podem envolver diferentes recursos e, por isso, apresentam as seguintes definições:

Consultas simples;
Consultas baseadas em condições simples ou compostas;
Consultas que recuperam dados de diferentes tabelas (junções);
Consultas que utilizam funções para realização de diferentes operações;
Consultas que manipulam grupos de dados;
Consultas baseadas no resultado de outras consultas.
A instrução utilizada para a realização das consultas é o SELECT, que faz parte da categoria de operações DML (Data Manipulation Language).

Alguns autores criam um grupo à parte para tratar somente do SELECT, o DQL, Data Query Language (Linguagem de Consulta de Dados) ou DRL, Data Retrieve Language (Linguagem de Recuperação de Dados).



## Comandos e Elementos da Instrução SELECT em SQL

* **SELECT**: Especifica as colunas (campos) necessários para a pesquisa.
* **DISTINCT**: Não mostra eventuais valores repetidos de colunas.
* **ALL**: Mostra todos os valores, mesmo que repetidos; esse é o padrão se o DISTINCT não for definido, portanto, não precisamos escrevê-lo.
* `*` (asterisco): Indica que devem ser mostradas todas as colunas da tabela.
* **FROM**: Indica em que tabelas serão efetuadas estas pesquisas.
* **WHERE**: Condição para que se execute a pesquisa (filtra dados).
* **ORDER BY**: Especifica em que ordem deverá ser apresentada a pesquisa desejada; por qual campo estará ordenada (de forma crescente ou decrescente).
* `<nome-tabela>`: Tabela que terá os dados recuperados.
* `<nome-coluna>`: Colunas que serão recuperadas da tabela.
* `<condição>`: Condição (filtro) utilizado no momento da recuperação dos dados da tabela.

## Operadores Aritméticos em SQL

Os operadores aritméticos são utilizados nas instruções SQL.

Sempre que houver mais de um operador, a precedência matemática será respeitada, ou seja, a multiplicação e a divisão serão avaliadas em primeiro lugar, e o uso dos parênteses pode alterar a ordem de execução dos operadores.

| OPERADOR | DESCRIÇÃO    |
|----------|--------------|
| +        | Adição       |
| -        | Subtração    |
| * | Multiplicação|
| /        | Divisão      |

### Exemplos de comando SELECT com operadores aritméticos:

O comando `SELECT` retornará apenas as colunas declaradas da tabela `FUNCIONARIO`.

Observe que estamos realizando um cálculo, durante a declaração das colunas no comando `SELECT`, portanto serão recuperados todos os funcionários cadastrados e ainda será realizado o cálculo de 5% de aumento do salário mensal.


## ALIAS - APELIDO PARA COLUNAS

Às vezes, ao recuperar dados através de um comando `SELECT`, o nome da coluna (campo) não é muito claro ou apropriado para a apresentação dos dados. Os apelidos são úteis para melhorar a legibilidade do resultado da consulta, facilitando o entendimento por parte do usuário, portanto, é possível renomear o cabeçalho (rótulo) da coluna que será recuperada.

Por isso, podemos usar um “apelido” para a coluna, que chamamos de **ALIAS**.

É muito útil quando queremos retornar um nome adequado para o resultado de um cálculo, por exemplo.

**Regras para definir um ALIAS:**

* Deve ser escrito **após** o nome da coluna ou cálculo.
* Se for uma **palavra composta**, ou tenha **caracteres especiais** (acentos, por exemplo) ou que faça **distinção entre maiúsculas e minúsculas**, deve ser escrito **entre aspas duplas** (`"`).
* É importante ressaltar que **não deve ser uma palavra reservada** (SELECT, WHERE, etc.).
* Podemos utilizar o **"AS" (opcional)** para explicitar o apelido de uma coluna.

**Exemplo de consulta utilizando ALIAS para colunas:**

(O exemplo de consulta em SQL não foi fornecido na imagem.)


## CLÁUSULA ORDER BY

O resultado de uma consulta pode ser apresentado de forma ordenada (classificada), utilizando a cláusula `ORDER BY`.

A cláusula `ORDER BY` é utilizada para classificar (ordenar) as linhas recuperadas por uma consulta. Podemos especificar uma ou mais colunas para classificar (ordenar) os dados de uma tabela.

Essa cláusula é declarada no final de um comando `SELECT` e pode ordenar o resultado em ordem **ascendente** (`ASC`), que é a opção "DEFAULT", e **descendente** (`DESC`).

A cláusula `ORDER BY` aceita números representando a coluna na ordem em que foi declarada na cláusula `SELECT`, além de aceitar o `ALIAS` (apelido), caso tenha sido dado a alguma coluna.

O comando `SELECT` retornará apenas as colunas declaradas e todas as linhas da tabela `DEPARTAMENTO`. As linhas serão retornadas conforme a classificação fornecida na instrução SQL.

**Exemplo:**

Neste exemplo, serão recuperados todos os departamentos cadastrados e ordenados de forma ascendente (crescente), por nome do departamento.

(O exemplo de código SQL não foi fornecido na imagem.)

## CONSULTA EM TABELAS UTILIZANDO FILTROS

Ao inserir filtros na consulta das tabelas, utilizamos **operadores** para criar essas condições.

Esses operadores funcionam como **condições que precisam ser satisfeitas** para que os dados sejam recuperados.

Os operadores são utilizados para estabelecer uma **relação de comparação entre valores ou expressões**, resultando sempre em um **valor lógico (booleano)**, sendo verdadeiro ou falso.

Os operadores podem ser utilizados em **consultas**, **atualizações** ou **exclusões de dados**.

## OPERADORES RELACIONAIS

Os operadores relacionais são utilizados para realizar comparações entre valores em estruturas de controle.

São operadores relacionais na linguagem SQL:

| OPERADOR | SIGNIFICADO      | EXEMPLO      |
|----------|------------------|--------------|
| =        | Igual            | `codigo=2`   |
| <        | Menor que        | `preco<10`   |
| <=       | Menor ou igual a | `preco<=10`  |
| >        | Maior que        | `preco>10`   |
| >=       | Maior ou igual a | `preco>=10`  |
| `<>` ou `!=` | Diferente        | `codigo<>2`  |

### Exemplos de comando SELECT com operadores relacionais:

(Os exemplos de código SQL não foram fornecidos na imagem.)

## OPERADORES LÓGICOS

Os operadores lógicos são utilizados para filtrar linhas de uma base de dados, utilizando mais de uma condição.

* O operador **AND** recupera uma linha, se **todas** as condições separadas por AND forem verdadeiras.
* O operador **OR** recupera uma linha, se **qualquer uma** das condições separadas por OR forem verdadeiras.
* O operador **NOT** recupera uma linha, se a condição (s) **não** for verdadeira.

São operadores lógicos, na linguagem SQL:

| OPERADOR | DESCRIÇÃO                                  |
|----------|--------------------------------------------|
| AND      | Retorna TRUE se ambas condições forem verdadeiras |
| OR       | Retorna TRUE se ao menos uma das condições for verdadeira |
| NOT      | Retorna TRUE se a condição for falsa       |

### Exemplos de comando SELECT com operadores lógicos:

(Os exemplos de código SQL não foram fornecidos na imagem.)

## OPERADORES ESPECIAIS OU OPERADORES SQL

Os operadores SQL permitem limitar as linhas recuperadas com base na correspondência de padrão de *strings*, listas de valores, intervalos de valores e valores nulos.

São operadores especiais, na linguagem SQL:

| OPERADOR        | DESCRIÇÃO                              |
|-----------------|----------------------------------------|
| BETWEEN ... AND | Entre dois valores (inclusive)         |
| IN (*lista*)    | Compara o valor de uma coluna com um conjunto de valor |
| LIKE *valor* | Compara cadeia de caracteres           |
| IS NULL / IS NOT NULL | É um valor nulo. Não nulo         |

### Exemplos de comando SELECT com operadores especiais:

(Os exemplos de código SQL não foram fornecidos na imagem.)

## O Operador LIKE em SQL

O operador especial ou SQL `LIKE` é utilizado para recuperar linhas, quando se deseja procurar um padrão em uma *string*. Os padrões são especificados usando uma combinação de caracteres normais e os dois caracteres curinga a seguir:

* **Sublinhado (\_):** Corresponde a um caractere em uma posição específica.
* **Porcentagem (%):** Corresponde a qualquer número de caracteres a partir da posição especificada.

| EXPRESSÃO   | DESCRIÇÃO                                                                 |
|-------------|---------------------------------------------------------------------------|
| `LIKE 'A%'` | Todas as palavras que iniciam a letra A.                                 |
| `LIKE '%A'` | Todas as palavras que terminam com a letra A.                              |
| `LIKE '%A%'`| Todas as palavras que tenham a letra A em qualquer posição.               |
| `LIKE 'A_'` | String de dois caracteres que tenham a primeira letra A e o segundo caractere seja qualquer um. |
| `LIKE '_A'` | String de dois caracteres cujo primeiro seja qualquer um e a última letra seja A. |
| `LIKE '_A_'`| String de três caracteres cuja segunda letra seja A independentemente do primeiro ou do último caractere. |
| `LIKE '%A_'`| Todas as palavras que tenham a letra A na penúltima posição e a última seja qualquer outro caractere. |
| `LIKE '_A%'`| Todos que tenham a letra A na segunda posição e o primeiro caractere seja qualquer um. |



## ANÁLISE TOP-N

Análise TOP-N é um tipo de consulta bastante útil em situações em que precisamos encontrar, por exemplo, os "N" maiores ou menores elementos dentro de determinado grupo: os funcionários mais bem pagos, os que vendem mais, as mercadorias menos vendidas e assim por diante.

Para conseguirmos isso no Oracle, precisamos implementar uma consulta interna (*subquery*) que retornará todos os registros/linhas necessários, e na consulta externa limitaremos a exibição em um total desejado. Este processo é conhecido como consulta TOP-N no Oracle.

### Exemplo de consulta utilizando análise TOP-N:

Uma *subquery* (consulta interna) recupera todos os salários de funcionários em ordem decrescente (maior para o menor). A consulta externa apresenta os dados retornados da consulta interna, limitando nas três primeiras linhas. A limitação é feita através da cláusula `WHERE`, na qual validamos a quantidade de linhas recuperadas em um total menor ou igual a três.

```sql
-- PARA EXIBIR OS NOMES E OS SALÁRIOS DOS
-- TRÊS FUNCIONÁRIOS MAIS BEM REMUNERADOS
-- DA TABELA FUNCIONARIO.
SELECT  ROWNUM as RANK ,
        NM_FUNCIONARIO ,
        VL_SALARIO_MENSAL
FROM
    (   SELECT NM_FUNCIONARIO ,
                VL_SALARIO_MENSAL
            FROM T_SIP_FUNCIONARIO
        ORDER BY VL_SALARIO_MENSAL DESC
    )
WHERE ROWNUM <= 3;