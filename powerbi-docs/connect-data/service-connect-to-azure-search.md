---
title: Conectar-se ao Azure Search com o Power BI
description: Azure Search para o Power BI
author: SarinaJoan
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 11389b5986d0dd627b0077808a74db5ab2769a65
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2020
ms.locfileid: "86216305"
---
# <a name="connect-to-azure-search-with-power-bi"></a>Conectar-se ao Azure Search com o Power BI
A Análise de Tráfego do Azure Search permite que você monitore e entenda o tráfego para o serviço de Azure Search. O pacote de conteúdo de Azure Search para o Power BI fornece informações detalhadas sobre seus dados de pesquisa, incluindo Search, Indexação, Status do Serviço e a Latência dos últimos 30 dias. Mais detalhes podem ser encontrados na [postagem do blog do Azure](https://azure.microsoft.com/blog/analyzing-your-azure-search-traffic/).

[!INCLUDE [include-short-name](../includes/service-deprecate-content-packs.md)]

Conectar-se ao [pacote de conteúdo do Azure Search](https://app.powerbi.com/getdata/services/azure-search) para o Power BI.

## <a name="how-to-connect"></a>Como conectar-se
1. Selecione **Obter Dados** na parte inferior do painel de navegação.
   
   ![Captura de tela de Obter Dados no Power BI Desktop mostrando o botão no painel do navegador.](media/service-connect-to-azure-search/pbi_getdata.png) 
2. Na caixa **Serviços** , selecione **Obter**.
   
   ![Captura de tela da caixa de diálogo Serviços mostrando o botão Obter.](media/service-connect-to-azure-search/pbi_getservices.png) 
3. Selecione **Azure Search** \> **Obter**.
   
   ![Captura de tela da caixa de diálogo Serviços do Azure mostrando o link Obter.](media/service-connect-to-azure-search/azuresearch.png)
4. Forneça o nome da conta de armazenamento de tabela na qual sua análise do Azure Search está armazenada.
   
   ![Captura de tela da caixa de diálogo Conectar o Azure Search mostrando o campo de nome da conta de armazenamento do Azure.](media/service-connect-to-azure-search/params.png)
5. Selecione **Chave** como Mecanismo de Autenticação e forneça sua chave de conta de armazenamento. Clique em **Entrar** para iniciar o processo de carregamento.
   
   ![Captura de tela da caixa de diálogo Conectar o Azure Search mostrando que a Chave foi inserida no campo Método de autenticação.](media/service-connect-to-azure-search/creds.png)
6. Quando o carregamento for concluído, um novo dashboard, relatório e modelo aparecerão no painel de navegação. Selecione o painel para exibir os dados importados por você.
   
    ![Captura de tela do painel de navegação mostrando o dashboard, o relatório e o modelo.](media/service-connect-to-azure-search/dashboard2.png)

**E agora?**

* Tente [fazer uma pergunta na caixa de P e R](../consumer/end-user-q-and-a.md) na parte superior do dashboard
* [Altere os blocos](../create-reports/service-dashboard-edit-tile.md) no dashboard.
* [Selecione um bloco](../consumer/end-user-tiles.md) para abrir o relatório subjacente.
* Enquanto seu conjunto de dados será agendado para ser atualizado diariamente, você pode alterar o agendamento de atualização ou tentar atualizá-lo sob demanda usando **Atualizar Agora**

## <a name="system-requirements"></a>Requisitos do sistema
O pacote de conteúdo de Azure Search exige que a Análise de Tráfego do Azure Search esteja habilitada na conta.

## <a name="troubleshooting"></a>Solução de problemas
Certifique-se de que o nome da conta de armazenamento seja fornecido corretamente com a chave de acesso completo. O nome da conta de armazenamento deve corresponder à conta configurada com a Análise de Tráfego do Azure Search.

## <a name="next-steps"></a>Próximas etapas
[O que é o Power BI?](../fundamentals/power-bi-overview.md)

[Conceitos básicos para designers no serviço do Power BI](../fundamentals/service-basic-concepts.md)
