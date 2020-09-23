---
title: 'DAX: Usar COUNTROWS em vez de COUNT'
description: Orientações sobre como usar as funções COUNTROWS.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/23/2019
ms.author: v-pemyer
ms.openlocfilehash: 1a49531c9c7e525371c3c92b7bf116bfa7e99fd3
ms.sourcegitcommit: cff93e604e2c5f24e0f03d6dbdcd10c2332aa487
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90965531"
---
# <a name="dax-use-countrows-instead-of-count"></a>DAX: Usar COUNTROWS em vez de COUNT

Como modelador de dados, às vezes você pode precisar escrever uma expressão DAX que conta as linhas de uma tabela. A tabela pode ser uma tabela de modelo ou uma expressão que retorna uma tabela.

Isso pode ser feito de duas maneiras. Você pode usar a função [COUNT](/dax/count-function-dax) para contar valores de coluna ou pode usar a função [COUNTROWS](/dax/countrows-function-dax) para contar linhas de tabela. As duas funções chegarão ao mesmo resultado, desde que a coluna contada não contenha nenhum valor EM BRANCO.

A definição de medida a seguir é um exemplo. Ela calcula o número de valores de coluna **OrderDate**.

```dax
Sales Orders =
COUNT(Sales[OrderDate])
```

Desde que a granularidade na tabela de **Vendas** seja de uma linha por ordem de venda, e que a coluna **OrderDate** não contenha valores EM BRANCO, a medida retornará um resultado correto.

Entretanto, a definição de medida a seguir é um resultado melhor.

```dax
Sales Orders =
COUNTROWS(Sales)
```

Há três motivos que fazem com que a segunda definição de medida seja melhor:

- Ela é mais eficiente e, portanto, terá um desempenho melhor.
- Ela não considera os valores EM BRANCO em qualquer coluna da tabela.
- A intenção da fórmula é mais clara, chegando a ser autodescritivo.

## <a name="recommendation"></a>Recomendação

Quando sua intenção é contar as linhas da tabela, recomendamos sempre usar a função COUNTROWS.

## <a name="next-steps"></a>Próximas etapas

Para obter mais informações sobre este artigo, confira os seguintes recursos:

- [Referência do DAX (Data Analysis Expressions)](/dax/)
- Roteiro de aprendizagem: [Usar o DAX no Power BI Desktop](/learn/paths/dax-power-bi/)
- Perguntas? [Experimente perguntar para a Comunidade do Power BI](https://community.powerbi.com/)
- Sugestões? [Contribuir com ideias para aprimorar o Power BI](https://ideas.powerbi.com)