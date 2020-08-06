---
title: Colaborar no Microsoft Teams com o Power BI
description: É fácil compartilhar e colaborar em conteúdos interativos do Power BI em canais e chats do Microsoft Teams.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 07/31/2020
ms.openlocfilehash: 01e5b470e0beb189d64da18785a17e771bcaf59b
ms.sourcegitcommit: d9d67ee47954379c2df8db8d0dc8302de4c9f1e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "87478028"
---
# <a name="collaborate-in-microsoft-teams-with-power-bi"></a>Colaborar no Microsoft Teams com o Power BI

Conforme uma força de funcionários distribuída e remota está se tornando a norma, cada vez mais organizações estão contando com o Microsoft Teams para manter os funcionários em sincronia. O Power BI oferece várias opções para compartilhar e colaborar em conteúdos interativos do Power BI em canais e chats do Microsoft Teams. 

- Com a guia **Power BI** no Microsoft Teams, você pode [inserir relatórios interativos em canais e chats do Microsoft Teams](service-embed-report-microsoft-teams.md). A guia **Power BI** ajuda seus colegas a encontrar os dados de sua equipe e a discutir os dados nos canais de sua equipe. 
- Crie uma [visualização de link](service-teams-link-preview.md) quando você colar um link para seus relatórios, dashboards e aplicativos na caixa de mensagem do Microsoft Teams. A visualização de link mostra informações sobre o link. 
- Use [Compartilhar no Teams](service-share-report-teams.md) ao exibir relatórios e dashboards no serviço do Power BI para iniciar conversas rapidamente no Teams.
 
:::image type="content" source="media/service-collaborate-microsoft-teams/power-bi-embed-teams-report.png" alt-text="Captura de tela de um relatório do Power BI inserido em um canal do Teams.":::

## <a name="requirements"></a>Requisitos

De modo geral, para que o Power BI funcione no Microsoft Teams, assegure os seguintes elementos:

- Os usuários têm uma licença do Power BI Pro ou se o relatório está contido em uma [capacidade do Power BI Premium (SKU P ou EM)](../admin/service-premium-what-is.md) com uma licença do Power BI.
- Os usuários entraram no serviço do Power BI para ativar suas licenças do Power BI.
- Os usuários atendem aos requisitos para usar a guia **Power BI** no Microsoft Teams.

## <a name="grant-access-to-reports"></a>Conceder acesso aos relatórios

A inserção de um relatório no Microsoft Teams ou o envio de um link a um item não concede automaticamente aos usuários permissão para ver o relatório. Você precisa [permitir que os usuários exibam o relatório no Power BI](service-share-dashboards.md). Para facilitar, você pode usar um Grupo do Microsoft 365 para sua equipe.

> [!IMPORTANT]
> Certifique-se de examinar quem pode ver o relatório dentro do serviço do Power BI e de conceder acesso aos que não aparecem na lista.

Uma forma de garantir que todos em uma equipe tenham acesso aos relatórios é colocá-los em um único workspace e dar à equipe acesso ao Grupo do Microsoft 365.

## <a name="known-issues-and-limitations"></a>Limitações e problemas conhecidos

- O Power BI não dá suporte aos mesmos idiomas localizados que o Microsoft Teams. Como resultado, talvez você não veja uma localização adequada dentro do relatório inserido.
- Os dashboards do Power BI não podem ser inseridos na guia do **Power BI** do Microsoft Teams.
- Os usuários sem uma licença ou permissão do Power BI para acessar o relatório veem a mensagem "O conteúdo não está disponível".
- Você poderá ter problemas se usar o Internet Explorer 10. <!--You can look at the [browsers support for Power BI](../consumer/end-user-browsers.md) and for [Microsoft 365](https://products.office.com/office-system-requirements#Browsers-section). -->
- Não há suporte para os [filtros de URL](service-url-filters.md) na guia **Power BI** para o Microsoft Teams.
- Em nuvens nacionais, a nova guia do **Power BI** não está disponível. Pode estar disponível uma versão mais antiga que não dá suporte à nova experiência de workspace nem a relatórios em aplicativos do Power BI.
- Depois de salvar a guia, você não poderá alterar o nome da guia por meio das configurações dela. Use a opção **Renomear** para alterá-lo.
- Não há suporte para logon único no serviço de visualização de link.
- As visualizações de link não funcionam em chat de reuniões ou canais privados.

## <a name="next-steps"></a>Próximas etapas

- [Inserir conteúdo do Power BI no Microsoft Teams](service-embed-report-microsoft-teams.md)
- [Obter uma visualização de link do Power BI no Microsoft Teams](service-teams-link-preview.md)
- [Compartilhar diretamente com o Teams do serviço do Power BI](service-share-report-teams.md)

Mais perguntas? [Experimente perguntar à Comunidade do Power BI](https://community.powerbi.com/).
