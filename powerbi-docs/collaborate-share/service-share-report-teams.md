---
title: Compartilhar diretamente com o Teams do serviço do Power BI
description: Você pode compartilhar dashboards e relatórios do Power BI diretamente com o Microsoft Teams por meio do serviço do Power BI.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
LocalizationGroup: Share your work
ms.date: 07/31/2020
ms.openlocfilehash: 0152f835f130eaea12addee1cc8daa15975d7aa1
ms.sourcegitcommit: d9d67ee47954379c2df8db8d0dc8302de4c9f1e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "87478051"
---
# <a name="share-directly-to-teams-from-the-power-bi-service"></a>Compartilhar diretamente com o Teams do serviço do Power BI

Você pode compartilhar dashboards, relatórios e visuais do Power BI diretamente com o Microsoft Teams por meio do serviço do Power BI. Use o recurso **Compartilhar com o Teams** para iniciar conversas rapidamente ao exibir relatórios e dashboards no serviço do Power BI.

## <a name="requirements"></a>Requisitos

Para usar o a funcionalidade **Compartilhar com o Teams** no Power BI, assegura esta configuração:

- Os administradores do Power BI não desabilitaram a configuração de locatário **Compartilhar no Teams** no portal de administração do Power BI. Essa configuração permite que as organizações ocultem os botões **Compartilhar com o Teams**. Confira o artigo [Portal de administração do Power BI](../admin/service-admin-portal.md#share-to-teams-tenant-setting) para obter detalhes.

Confira [Colaborar no Microsoft Teams com o Power BI](service-collaborate-microsoft-teams.md) para saber como o Power BI e o Teams funcionam juntos, incluindo outros requisitos.

## <a name="share-power-bi-content-to-teams"></a>Compartilhar conteúdo do Power BI no Teams

Siga estas etapas para compartilhar links para relatórios, dashboards e visuais no serviço do Power BI com canais e chats do Microsoft Teams.

1. Selecione uma destas opções:

   * **Compartilhar com o Teams** na barra de ação de um dashboard ou relatório:

       ![Captura de tela do botão Compartilhar com o Teams na barra de ação.](media/service-share-report-teams/service-teams-share-to-teams-action-bar-button.png)
    
   * **Compartilhar com o Teams** no menu de contexto de um visual:
    
      ![Captura de tela do botão Compartilhar com o Teams no menu contextual de um visual.](media/service-share-report-teams/service-teams-share-to-teams-visual-context-menu.png)

1. Na caixa de diálogo **Compartilhar no Microsoft Teams**, selecione o canal ou as pessoas para os quais você quer enviar o link. Insira uma mensagem, se desejar. Você pode ser solicitado a entrar no Microsoft Teams primeiro.

    ![Captura de tela da caixa de diálogo Compartilhar com o Microsoft Teams com informações e mensagem.](media/service-share-report-teams/service-teams-share-to-teams-dialog.png)

1. Selecione **Compartilhar** para enviar o link.
    
1. O link é adicionado a conversas existentes ou inicia um novo chat.

    ![Captura de tela de conversa do Microsoft Teams com link para um item do Power BI.](media/service-share-report-teams/service-teams-share-to-teams-deep-link.png)

1. Selecione o link para abrir o item no serviço do Power BI.

1. Se você tiver usado o menu contextual para um visual específico, o visual será realçado quando o relatório for aberto.

    ![Captura de tela de relatório do Power BI aberto com um visual específico realçado.](media/service-share-report-teams/service-teams-share-to-teams-spotlight-visual.png)


## <a name="known-issues-and-limitations"></a>Limitações e problemas conhecidos

- Os usuários sem uma licença ou permissão do Power BI para acessar o relatório veem a mensagem "O conteúdo não está disponível".
- Os botões **Compartilhar no Teams** poderão não funcionar se o seu navegador usar configurações de privacidade estritas. Use a opção **Está com problemas? Tente abrir em uma nova janela** se a caixa de diálogo não abrir corretamente.
- O **Compartilhar no Teams** não inclui uma visualização de link.
- As visualizações de link e o **Compartilhar no Teams** não dão aos usuários permissões para exibir o item. As permissões devem ser gerenciadas separadamente.
- O botão **Compartilhar com o Teams** não fica disponível nos menus de contexto dos visuais quando o autor do relatório define **Mais opções** como **Desativado** no visual.
- Confira a seção [Limitações e problemas conhecidos](service-collaborate-microsoft-teams.md#known-issues-and-limitations) do artigo "Colaborar no Microsoft Teams" para ver outros problemas.

## <a name="next-steps"></a>Próximas etapas

- [Colaborar no Microsoft Teams com o Power BI](service-collaborate-microsoft-teams.md)

Mais perguntas? [Experimente perguntar à Comunidade do Power BI](https://community.powerbi.com/).
