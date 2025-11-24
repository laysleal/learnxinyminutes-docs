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

/////////////
// MEDIDAS
/////////////

// Medidas são fórmulas criadas com a linguagem DAX para realizar cálculos
// como soma ou média, que retornam um único valor e se adaptam a filtros.

// Uma medida pode usar funções DAX de agregação, data e hora,
// inteligência de tempo, lógica, texto, tabela, iteração,
// matemática e estatística, informação de valores, relacionamento,
// manipulação de filtros e contexto, parent/child, ranking e também de
// funções especiais próprias da linguagem.

// Medidas criadas podem ser utilizadas como argumento para outras medidas.

Quando você define uma fórmula para uma medida na barra de fórmulas, um recurso de Dica de Ferramenta mostra uma visualização de quais seriam os resultados para o total no contexto atual, mas caso contrário, os resultados não são imediatamente gerados em qualquer lugar. O motivo pelo qual você não pode ver os resultados (filtrados) do cálculo imediatamente é porque o resultado de uma medida não pode ser determinado sem contexto. Para avaliar uma medida, é necessário um aplicativo cliente de relatório que possa fornecer o contexto necessário para recuperar os dados relevantes para cada célula e, em seguida, avaliar a expressão para cada célula. Esse cliente pode ser uma Tabela Dinâmica ou um Gráfico Dinâmico do Excel, um relatório do Power BI ou uma expressão de tabela em uma consulta DAX no SSMS (SQL Server Management Studio).

Independentemente do cliente, uma consulta separada é executada para cada célula nos resultados. Ou seja, cada combinação de cabeçalhos de linha e coluna em uma Tabela Dinâmica ou cada seleção de segmentações e filtros em um relatório do Power BI gera um subconjunto diferente de dados sobre os quais a medida é calculada. Por exemplo, usando esta fórmula de medida muito simples:

/////////////
// FUNÇÕES
/////////////



