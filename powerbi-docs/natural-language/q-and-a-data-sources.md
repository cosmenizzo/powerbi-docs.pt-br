---
title: Usar linguagem natural com importação, Live Connect e Direct Query
description: Neste artigo, veremos como o recurso de P e R funciona com os diferentes tipos de fontes de dados disponíveis no Power BI. Também vamos examinar os conceitos de indexação e cache.
author: mohaali
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/19/2020
ms.author: mohaali
ms.openlocfilehash: 85ecc5adc55daee86922c39e417db1cac5ba4a52
ms.sourcegitcommit: 0f807d3c74e5202b6e6a95fad49f2787928b9613
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/21/2020
ms.locfileid: "88706181"
---
# <a name="use-natural-language-with-import-live-connect-and-direct-query"></a>Usar linguagem natural com importação, Live Connect e Direct Query

O recurso P e R do Power BI permite que você obtenha rapidamente respostas de seus dados usando linguagem natural para fazer perguntas sobre esses dados. Este artigo descreve como a indexação e o cache são usados para melhorar o desempenho de cada configuração compatível.

## <a name="what-data-sources-are-supported-in-qa"></a>Quais fontes de dados têm suporte no P e R?

O P e R tem suporte nas seguintes configurações:

- Modo de importação
- Modo de conexão dinâmica – usando conjuntos de dados do SQL Server Analysis Services, Azure Analysis Services ou Power BI locais
- Direct Query – Azure Synapse, Azure SQL e SQL Server 2019. Embora outras fontes possam funcionar no modo de consulta direta, não damos suporte oficialmente a essas fontes.

Por padrão, P e R será habilitado dentro de um relatório se você usar um visual do P e R. Um prompt será exibido se você estiver usando Direct Query ou Live Connect. Você pode ativar/desativar explicitamente as funcionalidades de idioma natural de um relatório entrando em opções.

![Opções de área de trabalho do P e R](media/qna-desktop-options.png)

Para obter mais informações, confira [Limitações de P e R do Power BI](q-and-a-limitations.md).

## <a name="how-does-indexing-work-with-qa"></a>Como funciona a indexação com P e R?

Quando você habilita o P e R, um índice é criado para fornecer rapidamente comentários em tempo real para o usuário e para ajudar a interpretar as perguntas do usuário. O índice pode levar algum tempo para ser criado e terá os seguintes elementos e limitações.

- Todos os nomes de coluna e tabelas são inseridos no índice, a menos que tenham sido explicitamente desativados na ferramenta de P e R.
- Todos os valores de texto com menos de 100 caracteres serão indexados. Valores de texto com mais de 100 caracteres não serão indexados. 
- O P e R armazenará, no máximo, 5 milhões valores exclusivos em seu índice. Se você exceder esse limite, o índice não conterá todos os valores possíveis, o que pode diminuir a precisão dos resultados recebidos do P e R.
- Se ocorrer um erro durante a indexação, o índice permanecerá em um estado parcial e será recriado na atualização seguinte, conforme descrito na próxima seção.

## <a name="how-often-is-the-index-refreshed-and-cached"></a>Com que frequência o índice é atualizado e armazenado em cache?

No Power BI Desktop, o índice é criado no momento em que você usa o P e R. Um pequeno ícone será exibido informando que o índice está sendo compilado. Durante esse tempo, o visual do P e R, incluindo sugestões, poderá levar algum tempo para carregar.

No serviço do Power BI, o índice é recriado na publicação/republicação e na atualização. O índice do P e R nem sempre é criado automaticamente. Às vezes, ele será criado sob demanda para otimizar as atualizações do conjunto de dados. Para o Direct Query, indexaremos os dados no máximo uma vez por dia para reduzir o impacto na origem do Direct Query.

## <a name="next-steps"></a>Próximas etapas

Você pode integrar o idioma natural a seus relatórios de várias maneiras. Para obter mais informações, confira estes tópicos:

* [Visual de P e R](../visuals/power-bi-visualization-q-and-a.md)
* [Melhores práticas de P e R](q-and-a-best-practices.md)
