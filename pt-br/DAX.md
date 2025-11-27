---
name: DAX
contributors:
    - ["Lays Leal Correia", "https://github.com/laysleal"]
---

A linguagem DAX (Data Analysis Expressions) nasceu dentro do ecossistema
Microsoft como parte do projeto de modelagem tabular lançado com o PowerPivot
para Excel. Depois veio a se tornar a linguagem principal do Power BI.

```dax
// Comentários em uma única linha começam com dupla barra, só é possível fazer
// comentários a partir da segunda linha de código.

/* Comentários de várias linhas podem ser escritas
    usando /*
    e finalizando com */
*/

// Fórmulas DAX são usadas principalmente para criar medidas, colunas e tabelas.

//////////////////////////////////
// MEDIDAS
//////////////////////////////////

// Medidas são fórmulas criadas com a linguagem DAX para realizar cálculos
// como soma ou média, que retornam um único valor e se adaptam a filtros.

// Uma medida pode usar funções DAX de agregação, data e hora,
// inteligência de tempo, lógica, texto, tabela, iteração,
// matemática e estatística, informação de valores, relacionamento,
// manipulação de filtros e contexto, parent/child, ranking e também
// funções especiais próprias da linguagem.

//////////////////////////////////
// OPERADORES E FUNÇÕES LÓGICAS
//////////////////////////////////

= //Igualdade
<> //Desigualdade
&& //AND
|| //OR

// Abaixo seguem algumas das mais utilizadas
TRUE()
FALSE()
AND()
OR()
NOT()
ISBLANK()
ISEMPTY()
IF()
COALESCE() //Funciona igual a função em SQL

//////////////////////////////////
// FUNÇÕES DAX
//////////////////////////////////

// O que está entre ' ' se refere a tabela, exemplo: 'BaseProdução'
// O que está entre [ ] se refere a uma coluna, exemplo: [Qtd Rejeitada]

// SUM soma todos os números de uma coluna.
SUM('BaseProdução'[Qtd Rejeitada])

// SUMX retorna a soma das colunas escolhidas em uma tabela
SUMX(
    'BaseProdução',
    'BaseProdução'[Qtd Aprovada] + 'BaseProdução'[Qtd Rejeitada]
)

//CALCULATE avalia uma expressão matemática de acordo com o filtro indicado
CALCULATE(
	SUM('BaseProdução'[Total Horas]),
	'BaseProdução'[Ocorrência] = "Manutenção"
)


