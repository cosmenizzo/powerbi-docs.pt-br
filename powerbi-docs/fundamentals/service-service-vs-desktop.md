---
title: Comparando o Power BI Desktop e o serviço do Power BI
description: O Power BI Desktop é uma ferramenta completa para criação de relatório e análise de dados. O serviço do Power BI é um serviço online, baseado em nuvem para equipes e empresas editarem relatórios e colaborarem neles de forma leve.
author: maggiesMSFT
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/07/2020
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 4118e5c009a8d7372d5cb58d1e1b9d033a70494e
ms.sourcegitcommit: 154946ece829360cc0ff3be13276cd7a129f3388
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87988726"
---
# <a name="comparing-power-bi-desktop-and-the-power-bi-service"></a>Comparando o Power BI Desktop e o serviço do Power BI

Em um diagrama de Venn que compara o Power BI Desktop e o serviço do Power BI, a área no meio mostra como os dois se sobrepõem. Algumas tarefas você pode fazer no Power BI Desktop ou no serviço. Os dois lados do diagrama de Venn mostram os recursos exclusivos do aplicativo e do serviço.  

![Diagrama de Venn mostrando a relação entre o Power BI Desktop e o serviço do Power BI.](media/service-service-vs-desktop/power-bi-venn-desktop-service.png)

O **Power BI Desktop** é uma ferramenta completa para criação de relatórios e análise de dados que você instala gratuitamente em seu computador local. Ele inclui o Editor de Consultas, em que você pode se conectar a várias fontes de dados diferentes e combiná-las em um modelo de dados (o que geralmente é chamado de modelagem). Em seguida, você designa um relatório com base no modelo de dados. O [guia de Introdução ao Power BI Desktop](desktop-getting-started.md) percorre esse processo.

O **serviço do Power BI** é um serviço baseado em nuvem. Ele dá suporte à edição e à colaboração de relatórios leves para equipes e organizações. Você também pode se conectar a fontes de dados no serviço do Power BI, mas a modelagem é limitada.

A maioria dos designers de relatórios do Power BI que trabalham em projetos de business intelligence usa o **Power BI Desktop** para criar relatórios do Power BI e o **Serviço do Power BI** para colaborar e distribuir seus relatórios.

O serviço do Power BI também hospeda *relatórios paginados* em worskpaces com suporte de uma capacidade do Power BI Premium. Para criar relatórios paginados, use o Power BI Report Builder. Confira [Comparar relatórios do Power BI e relatórios paginados](../paginated-reports/paginated-reports-report-builder-power-bi.md#compare-power-bi-reports-and-paginated-reports) no artigo "O que são relatórios paginados no Power BI Premium?" para obter mais informações.

## <a name="editing-power-bi-reports"></a>Editar relatórios do Power BI

Tanto no aplicativo quanto no serviço, os *relatórios* são criados e editados no Power BI. Um relatório pode ter uma ou várias páginas, com visuais e coleções de visuais. Adicione indicadores, botões, filtros e detalhamento para melhorar a navegação nos relatórios.

![Capturas de tela do Power BI Desktop e do serviço do Power BI, com as seções numeradas.](media/service-service-vs-desktop/power-bi-editing-desktop-service.png)

Os editores de relatório no Power BI Desktop e no serviço são semelhantes. Eles são formados por três seções:  

1. Os painéis de navegação superiores, diferentes no Power BI Desktop e no serviço    
2. A tela de relatório     
3. Os painéis **Campos**, **Visualizações** e **Filtros**

Este vídeo mostra o editor de relatório no Power BI Desktop. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

## <a name="working-in-the-power-bi-service"></a>Trabalhar no serviço do Power BI

### <a name="collaborating"></a>Colaborar

Depois de criar seus relatórios, você pode salvá-los em um *workspace* no **serviço do Power BI**, no qual você e seus colegas poderão colaborar. Os *dashboards* são criados com base nesses relatórios. Em seguida, compartilhe esses dashboards e relatórios com os consumidores de relatórios dentro e fora da organização. Os consumidores veem os relatórios no serviço do Power BI em um *Modo de exibição de leitura*, não no Modo de exibição de edição. Eles não têm acesso a todos os recursos disponíveis para os criadores de relatório.  Você também pode compartilhar seus conjuntos de dados e permitir que outras pessoas criem seus próprios relatórios com base neles. Leia mais sobre [como colaborar no serviço do Power BI](../collaborate-share/service-new-workspaces.md).

### <a name="self-service-data-prep-with-dataflows"></a>Preparação de dados de autoatendimento com fluxos de dados

Os fluxos de dados ajudam as organizações a unificar dados de diferentes fontes e prepará-los para serem modelados. Os analistas podem criar fluxos de dados facilmente, usando ferramentas conhecidas de autoatendimento. Os analistas usam fluxos de dados para ingerir, transformar, integrar e enriquecer Big Data definindo conexões de fonte de dados, lógica ETL, cronogramas de atualização e muito mais. Leia mais sobre [preparação de dados de autoatendimento com fluxos de dados](../transform-model/service-dataflows-overview.md).

## <a name="next-steps"></a>Próximas etapas

[O que é o Power BI Desktop?](desktop-what-is-desktop.md)

[Criar um relatório](../create-reports/service-report-create-new.md) no serviço do Power BI

[Conceitos básicos para designers de relatório](service-basic-concepts.md)

Mais perguntas? [Experimente a Comunidade do Power BI](https://community.powerbi.com/)
