---
title: Executar e exibir insights em blocos do painel
description: Como usuário final do Power BI, saiba como obter insights sobre seus blocos de painel.
author: mihart
ms.reviewer: mihart
featuredvideoid: et_MLSL2sA8
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 09/09/2020
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 21bccbd11f8d2060b648e22c8ed8aa9471c820f0
ms.sourcegitcommit: 002c140d0eae3137a137e9a855486af6c55ad957
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "89642516"
---
# <a name="view-data-insights-on-dashboard-tiles-with-power-bi"></a>Exibir insights de dados em blocos do painel com o Power BI

[!INCLUDE[consumer-appliesto-yyny](../includes/consumer-appliesto-yyny.md)]

Cada bloco de [visual](end-user-tiles.md) em seu dashboard é uma porta de entrada para exploração de dados. Quando você seleciona um bloco, ele abre um relatório ou [abre a seção de P e R](end-user-q-and-a.md), em que você pode filtrar, classificar e examinar o conjunto de dados do relatório. E quando você executa insights, o Power BI faz a exploração de dados para você.

![modo de menu de reticências mostrando Exibir insights como uma opção](./media/end-user-insights/power-bi-insight.png)

Execute insights para gerar visuais interativos e interessantes com base em seus dados. Insights podem ser executados em um bloco de dashboard específico, e você pode até mesmo executar insights em um insight.

O recurso Insights tem como base um crescente [conjunto de algoritmos analíticos avançados](end-user-insight-types.md), desenvolvido em conjunto com o Microsoft Azure for Research, os quais continuaremos a usar para permitir que mais pessoas encontrem informações em seus próprios dados de maneiras novas e intuitivas.

## <a name="run-insights-on-a-dashboard-tile"></a>Executar insights em um bloco do painel
Quando você executar insights em um bloco do dashboard, o Power BI pesquisa apenas os dados usados para criar esse bloco de dashboard único. 

1. [Abra um dashboard](end-user-dashboards.md).
2. Passe o mouse sobre um bloco. Selecione **Mais opções** (...) e **Exibir insights**. 

    ![Captura de tela mostrando que a seleção de reticências exibe a lista suspensa](./media/end-user-insights/power-bi-hover.png)


3. O bloco é aberto no [modo de foco](end-user-focus.md) com os cartões de insights exibidos à direita.    
   
    ![Modo de foco](./media/end-user-insights/power-bi-insights-tiles.png)    
4. Algum insight desperta seu interesse? Selecione esse cartão de insights para se aprofundar ainda mais. O insight selecionado aparece à esquerda e novos insights, com base apenas nos dados daquele único insight, são exibidos à direita.    

 ## <a name="interact-with-the-insight-cards"></a>Interagir com os cartões de insights
Depois que você tiver um insight aberto, continue a explorar.

   * Filtre esse visual na tela.  Para exibir os filtros, no canto superior direito, selecione a seta para expandir o painel Filtros.

      ![insight com o menu Filtros expandido](./media/end-user-insights/power-bi-filter.png)
   
   * Execute insights no cartão de insight em si. Isso é conhecido como **insights relacionados**. Selecione um cartão de insight para ativá-lo. Ele será movido para o lado esquerdo da tela do relatório, e os novos cartões, com base apenas nos dados desse único Insight, serão exibidos à direita.
   
      ![Insight relacionado e menu Filtros expandido](./media/end-user-insights/power-bi-insights-card.png)
   
     
Para retornar ao relatório, no canto superior esquerdo, selecione **Sair do modo de foco**.

## <a name="considerations-and-troubleshooting"></a>Considerações e solução de problemas
- **Exibir insights** não funciona com todos os tipos de bloco do dashboard. Por exemplo, ele não está disponível para visuais personalizados do Power BI.<!--[Power BI visuals](end-user-custom-visuals.md)-->


## <a name="next-steps"></a>Próximas etapas

Executar insights sobre visuais de relatórios [usando o recurso Analisar](end-user-analyze-visuals.md)    
Saiba mais sobre os [tipos de Insights disponíveis](end-user-insight-types.md)

