---
title: Conectar-se ao Office365Mon com o Power BI
description: Office365Mon para o Power BI
author: paulinbar
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: how-to
ms.date: 11/26/2019
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 422782c3036f94c1ea764f46135200116092d70c
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2020
ms.locfileid: "86216232"
---
# <a name="connect-to-office365mon-with-power-bi"></a>Conectar-se ao Office365Mon com o Power BI
Analisar seus dados de desempenho de integridade e interrupções do Office 365 é fácil com o Power BI e o aplicativo de modelo Office365Mon. O Power BI recupera seus dados, incluindo investigações de integridade e interrupções e, em seguida, compila um painel e relatórios prontos para uso com base em tais dados.

Conectar-se ao [aplicativo de modelo Office365Mon](https://msit.powerbi.com/groups/me/getapps/services/office365mon.office365mon_powerbi_v3) para Power BI.

>[!NOTE]
>Uma conta do administrador do Office365Mon é necessária para conectar e carregar o aplicativo de modelo Power BI.

## <a name="how-to-connect"></a>Como conectar-se
1. Selecione **Obter Dados** na parte inferior do painel de navegação.
   
   ![Captura de tela do botão Obter Dados mostrando-o no painel de navegação.](media/service-connect-to-office365mon/pbi_getdata.png)
2. Na caixa **Serviços** , selecione **Obter**.
   
   ![Captura de tela da caixa de diálogo Serviços mostrando o botão Obter.](media/service-connect-to-office365mon/pbi_getservices.png) 
3. Selecione **Office365Mon** \> **Obter**.
   
   ![Captura de tela da caixa de diálogo do Office365Mon mostrando o link Obter.](media/service-connect-to-office365mon/o365mon.png)
4. Para o Método de Autenticação, selecione **oAuth2** \> **Entrar**.
   
   Quando solicitado, insira suas credenciais de administrador do Office365Mon e siga o processo de autenticação.
   
   ![Captura de tela da caixa de diálogo Conectar ao Office365Mon mostrando OAuth2 no campo Método de Autenticação.](media/service-connect-to-office365mon/creds.png)
   
   ![Captura de tela da entrada do Office365Mon solicitando as credenciais.](media/service-connect-to-office365mon/creds2.png)
5. Após o Power BI importar os dados, você verá um novo dashboard, relatório e conjunto de dados no painel de navegação. Novos itens são marcados com um asterisco amarelo \*; selecione a entrada do Office365Mon.
   
   ![Captura de tela do painel de navegação no Power BI mostrando o dashboard, o relatório e o conjunto de dados.](media/service-connect-to-office365mon/dashboard4.png)

**E agora?**

* Tente [fazer uma pergunta na caixa de P e R](../consumer/end-user-q-and-a.md) na parte superior do dashboard
* [Altere os blocos](../create-reports/service-dashboard-edit-tile.md) no dashboard.
* [Selecione um bloco](../consumer/end-user-tiles.md) para abrir o relatório subjacente.
* Enquanto seu conjunto de dados será agendado para ser atualizado diariamente, você pode alterar o agendamento de atualização ou tentar atualizá-lo sob demanda usando **Atualizar Agora**

## <a name="troubleshooting"></a>Solução de problemas
Se você receber um erro **"falha no logon"** depois de usar suas credenciais de assinatura do Office365Mon para fazer logon, a conta sendo usada não tem permissões para recuperar os dados do Office365Mon de sua conta. Verifique se que ela é uma conta de administrador e tente novamente.

## <a name="next-steps"></a>Próximas etapas
[O que é o Power BI?](../fundamentals/power-bi-overview.md)

[Obter dados para o Power BI](service-get-data.md)
