---
title: Como encontrar a chave do produto (Product Key) do servidor de relatório
description: Saiba como você pode encontrar a chave do produto (Product Key) do Servidor de Relatório do Power BI para instalar o servidor em um ambiente de produção.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: how-to
ms.date: 10/24/2018
ms.author: maggies
ms.openlocfilehash: 86d3bf34a8b222e72d76a5471fe6bfca93390afc
ms.sourcegitcommit: 9350f994b7f18b0a52a2e9f8f8f8e472c342ea42
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90861120"
---
# <a name="how-to-find-your-report-server-product-key"></a>Como encontrar a chave do produto (Product Key) do servidor de relatório
Saiba como você pode encontrar a chave do produto (Product Key) do Servidor de Relatório do Power BI para instalar o servidor em um ambiente de produção.

<iframe width="640" height="360" src="https://www.youtube.com/embed/6CQnf-NGtpU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

Você baixou o Servidor de Relatório do Power BI e tem um contrato do Software Assurance do SQL Server Enterprise. Ou você comprou o Power BI Premium. Você deseja instalar o servidor em um ambiente de produção, mas precisa de uma chave do produto (Product Key) para fazer isso. Onde está a chave do produto (Product Key)? 

A chave do produto (Product Key) estará em um dos dois locais, dependendo do que você comprou.

## <a name="purchased-power-bi-premium"></a>Compra do Power BI Premium
Se você tiver adquirido o Power BI Premium, na da guia **Configurações de capacidade** do portal de administração do Power BI, você terá acesso à sua chave do produto do Servidor de Relatórios do Power BI. Isso somente estará disponível para os administradores globais ou usuários atribuídos à função de administrador de serviços do Power BI.

![Chave do Servidor de Relatórios do Power BI nas configurações Premium](media/find-product-key/pbirs-product-key.png)

Selecionar **chave do Servidor de Relatório do Power BI** exibirá uma caixa de diálogo que contém a chave do produto (Product Key). É possível copiá-la e usá-la com a instalação.

![Chave do produto (Product Key) do Servidor de Relatório do Power BI](media/find-product-key/pbirs-product-key-dialog.png)

## <a name="purchased-software-assurance-agreement"></a>Contrato do Software Assurance comprado
Se você tiver um contrato do SQL Server Enterprise SA, você poderá obter a chave do produto (Product Key) no [Centro de Serviços de Licenciamento por Volume](https://www.microsoft.com/Licensing/servicecenter/). Procure abaixo do último service pack para obter a última versão do SQL Server. Caso não a encontre, procure abaixo da versão RTM da última versão do SQL Server.

> [!NOTE]
> É necessário procure abaixo da seção de download. Não a seção de chaves.
> 
> 

![Captura de tela do SQL Server Enterprise mostrando a guia Downloads e Chaves com informações de integração de Relatório do Power BI.](media/find-product-key/vlsc-download.png "Centro de Serviços de Licenciamento por Volume")
 
## <a name="next-steps"></a>Próximas etapas
[Instalar o Servidor de Relatório do Power BI](install-report-server.md)  
[Instalar o Power BI Desktop otimizado para o servidor de relatórios do Power BI](install-powerbi-desktop.md)  
[Baixe o Construtor de Relatórios](https://www.microsoft.com/download/details.aspx?id=53613)  
[Baixar o SQL Server Data Tools (SSDT)](/sql/ssdt/download-sql-server-data-tools-ssdt)

Mais perguntas? [Experimente perguntar para a Comunidade do Power BI](https://community.powerbi.com/)