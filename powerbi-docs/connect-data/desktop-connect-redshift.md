---
title: Conectar-se a um banco de dados do Amazon Redshift no Power BI Desktop
description: Conectar-se facilmente e usar um banco de dados do Amazon Redshift no Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b832e96b795b38133939296a15dcab6ece3996be
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2020
ms.locfileid: "86214908"
---
# <a name="connect-to-an-amazon-redshift-database-in-power-bi-desktop"></a>Conectar-se a um banco de dados do Amazon Redshift no Power BI Desktop
No **Power BI Desktop**, é possível se conectar a um banco de dados do **Amazon Redshift** e usar os dados subjacentes, assim como qualquer outra fonte de dados no Power BI Desktop.

## <a name="connect-to-an-amazon-redshift-database"></a>Conectar-se a um banco de dados do Amazon Redshift
Para se conectar a um banco de dados do **Amazon Redshift**, selecione **Obter Dados** na faixa de opções **Página Inicial** no Power BI Desktop. Selecione **Banco de Dados** nas categorias à esquerda e você verá o **Amazon Redshift**.

![Captura de tela da caixa de diálogo Obter Dados mostrando a seleção de banco de dados do Amazon Redshift.](media/desktop-connect-redshift/connect_redshift_3.png)

Na janela **Amazon Redshift** que será mostrada, digite ou cole o nome do banco de dados e do servidor **Amazon Redshift** na caixa. Como parte do campo *Servidor*, os usuários podem especificar uma porta no seguinte formato: *URLdoServidor:Porta*

![Captura de tela da caixa de diálogo Amazon Redshift mostrando os campos Servidor e Banco de Dados.](media/desktop-connect-redshift/connect_redshift_4.png)

Quando solicitado, insira o nome de usuário e a senha. Você deve usar o nome do servidor que corresponde exatamente ao certificado SSL para evitar erros. 

![Captura de tela da solicitação de credenciais do Amazon Redshift mostrando os campos Nome de Usuário e Senha.](media/desktop-connect-redshift/connect_redshift_5.png)

Depois que você se conectar com êxito, uma janela **Navegador** será mostrada e exibirá os dados disponíveis no servidor, dentre os quais você pode selecionar um ou vários elementos para importar e usar no **Power BI Desktop**.

![Captura de tela da caixa de diálogo Navegador mostrando os dados disponíveis no servidor.](media/desktop-connect-redshift/connect_redshift_6.png)

Depois de fazer seleções na janela **Navegador**, você pode **Carregar** ou **Editar** os dados.

* Se você optar por **Carregar** os dados, será solicitado que você use o modo de *Importação* ou *DirectQuery* para carregar os dados. Para obter mais informações, confira este [artigo que explica o DirectQuery](desktop-use-directquery.md).
* Se você optar por **Editar** os dados, será mostrado o **Editor de Consultas**, no qual é possível aplicar todos os tipos de filtros e transformações aos dados, muitos dos quais são aplicados ao próprio banco de dados subjacente do **Amazon Redshift** (se houver suporte).

## <a name="next-steps"></a>Próximas etapas
Há todos os tipos de dados aos quais você pode se conectar usando o Power BI Desktop. Para obter mais informações sobre fontes de dados, confira os seguintes recursos:

* [O que é o Power BI Desktop?](../fundamentals/desktop-what-is-desktop.md)
* [Fontes de dados no Power BI Desktop](desktop-data-sources.md)
* [Formatar e combinar dados com o Power BI Desktop](desktop-shape-and-combine-data.md)
* [Conectar-se a pastas de trabalho do Excel no Power BI Desktop](desktop-connect-excel.md)   
* [Inserir dados diretamente no Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   
