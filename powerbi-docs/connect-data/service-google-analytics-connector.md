---
title: 'Serviço de terceiros: Conector do Google Analytics'
description: 'Serviço de terceiros: Conector do Google Analytics para Power BI Desktop'
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: ec290ce53155f24a9213a4849ecb82abd6cfc592
ms.sourcegitcommit: e8ed3d120699911b0f2e508dc20bd6a9b5f00580
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2020
ms.locfileid: "86263660"
---
# <a name="use-the-google-analytics-connector-for-power-bi-desktop"></a>Usar o conector do Google Analytics para o Power BI Desktop
> [!NOTE]
> O pacote de conteúdo do Google Analytics e o conector no Power BI Desktop dependem da API do Google Analytics Core Reporting. Por isso, os recursos e a disponibilidade podem variar ao longo do tempo.

É possível se conectar aos dados do Google Analytics usando o conector do **Google Analytics**. Para se conectar, siga essas etapas:

1. No **Power BI Desktop**, selecione **Obter Dados** na guia de faixa de opções **Página Inicial**.
2. Na janela **Obter Dados** janela, selecione **Serviços Online** das categorias no painel esquerdo.
3. Selecione **Google Analytics** com as seleções no painel à direita.
4. Na parte inferior da janela, selecione **Conectar**.  
   ![Captura de tela da guia Página Inicial mostrando a faixa de opções Obter Dados com o Google Analytics selecionado e o botão Conectar.](media/service-google-analytics-connector/tps_googleanalytics_1.png)

Você verá um diálogo que explica que o conector é um Serviço de Terceiro e que avisa sobre como os recursos e a disponibilidade podem ser alterados com o tempo, bem como outros esclarecimentos.  
![Captura de tela da caixa de diálogo de conexão mostrando um aviso informando que o conector depende de um Serviço de Terceiros.](media/service-google-analytics-connector/tps_googleanalytics_2.png)

Ao selecionar **Continuar**, você será solicitado a entrar no Google Analytics.  
![Captura de tela do aviso do Google Analytics mostrando que você precisa entrar para se conectar.](media/service-google-analytics-connector/tps_googleanalytics_3.png)

Ao digitar suas credenciais, você será notifica que o Power BI gostaria de ter acesso offline. É assim como você usa o **Power BI Desktop** para acessar seus dados do Google Analytics.  

Depois de aceitar, o **Power BI Desktop** mostra que você está conectado no momento.  
![Captura de tela do aviso do Google Analytics mostrando que você está conectado.](media/service-google-analytics-connector/tps_googleanalytics_5.png)

Selecione **Conectar** para que os dados do Google Analytics sejam conectados ao **Power BI Desktop** e carregados.  
![Captura de tela da caixa de diálogo Carregar mostrando que os dados do Google Analytics estão conectados e sendo carregados.](media/service-google-analytics-connector/tps_googleanalytics_6.png)

## <a name="changes-to-the-api"></a>Alterações no API
Podemos tentar lançar atualizações de acordo com as alterações, o API pode ser alterado de forma que afeta os resultados das consultas que gerarmos. Em alguns casos, determinadas consultas podem não ter mais suporte. Devido a essa dependência não podemos garantir os resultados de suas consultas ao usar esse conector.

Mais detalhes sobre as alterações na API do Google Analytics podem ser encontrados em seus [log de alterações](https://developers.google.com/analytics/devguides/changelog).

