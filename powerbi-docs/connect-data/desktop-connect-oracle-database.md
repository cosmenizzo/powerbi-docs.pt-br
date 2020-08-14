---
title: Conectar-se a um banco de dados Oracle com o Power BI Desktop
description: Etapas e downloads necessários para conectar o Oracle ao Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 08/11/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: f778b4f0c6572084598eb07df0e89b7a30aed7b1
ms.sourcegitcommit: d7145123133255d004b85ef8b20ca4977f0b843e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2020
ms.locfileid: "88091585"
---
# <a name="connect-to-an-oracle-database-with-power-bi-desktop"></a>Conectar-se a um banco de dados Oracle com o Power BI Desktop
Para se conectar a um banco de dados Oracle com o Power BI Desktop, o software cliente Oracle correto precisa estar instalado no computador que executa o Power BI Desktop. O software cliente Oracle usado depende da versão instalada do Power BI Desktop: 32 bits ou 64 bits. Ele também depende da versão do servidor Oracle.

Versões do Oracle com suporte: 
- Oracle Server 9 e posterior
- Software ODAC (Oracle Data Access Client) 11.2 e posterior

> [!NOTE]
> Se você estiver configurando um banco de dados Oracle para o Power BI Desktop, o Gateway de Dados Local ou o Servidor de Relatórios do Power BI, consulte as informações do artigo [Tipo de conexão Oracle](https://docs.microsoft.com/sql/reporting-services/report-data/oracle-connection-type-ssrs?view=sql-server-ver15). 


## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>Determinando qual versão do Power BI Desktop está instalada
Para determinar qual versão do Power BI Desktop está instalada, selecione **Arquivo** > **Ajuda** > **Sobre** e, em seguida, verifique a linha **Versão**. Na imagem a seguir, uma versão de 64 bits do Power BI Desktop está é instalada:

![Versão do Power BI Desktop](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="install-the-oracle-client"></a>Instalar o cliente Oracle
- Para a versão de 32 bits do Power BI Desktop, [baixe e instale o cliente Oracle de 32 bits](https://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html).

- Para a versão de 64 bits do Power BI Desktop, [baixe e instale o cliente Oracle de 64 bits](https://www.oracle.com/database/technologies/odac-downloads.html).

> [!NOTE]
> Escolha uma versão do ODAC (Oracle Data Access Client) que seja compatível com o Oracle Server. Por exemplo, o ODAC 12.x nem sempre dá suporte ao Oracle Server versão 9.
> Escolha o Windows Installer do Oracle Client.
> Durante a instalação do cliente Oracle, habilite a opção *Configurar os provedores ODP.NET e/ou Oracle para ASP.NET em nível de computador* marcando a caixa de seleção correspondente durante o assistente de instalação. Algumas versões do assistente de cliente Oracle marcam a caixa de seleção por padrão, outras não. Verifique se a caixa de seleção está selecionada para que Power BI possa se conectar ao seu banco de dados Oracle.

## <a name="connect-to-an-oracle-database"></a>Conectar-se a um banco de dados Oracle
Depois de instalar o driver do cliente Oracle correspondente, você poderá se conectar a um banco de dados Oracle. Para fazer a conexão, execute as seguintes etapas:

1. Na guia **Página Inicial**, selecione **Obter Dados**. 

2. Na janela **Obter Dados** exibida, selecione **Mais** (se necessário), **Banco de Dados** > **Oracle Database** e, em seguida, **Conectar**.
   
   ![Conectar Oracle Database](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
3. Na caixa de diálogo **Oracle Database** exibida, forneça o nome do **Servidor** e selecione **OK**. Se um SID for necessário, especifique-o usando o formato: *Nome_do_Servidor/SID*, em que *SID* é o nome exclusivo do banco de dados. Se o formato *Nome_do_Servidor/SID* não funcionar, use *Nome_do_Servidor/Nome_do_Serviço*, em que *Nome_do_Serviço* é o alias usado na conexão.


   ![Inserir o nome do servidor Oracle](media/desktop-connect-oracle-database/connect-oracle-database_3.png)

   > [!NOTE]
   > Se você está usando um banco de dados local ou uma conexão de banco de dados autônoma, convém colocar o nome do servidor entre aspas para evitar erros de conexão. 
      
4. Caso deseje importar dados usando uma consulta de banco de dados nativa, coloque a consulta na caixa **Instrução SQL**, exibida ao expandir a seção **Opções avançadas** da caixa de diálogo **Oracle Database**.
   
   ![Expandir Opções avançadas](media/desktop-connect-oracle-database/connect-oracle-database_4.png)


5. Depois de inserir as informações do Oracle Database na caixa de diálogo **Oracle Database** (incluindo informações opcionais, como um SID ou uma consulta de banco de dados nativa), selecione **OK** para se conectar.
5. Se o banco de dados Oracle exigir credenciais de usuário do banco de dados, insira as credenciais na caixa de diálogo quando solicitado.


## <a name="troubleshooting"></a>Solução de problemas

Você pode encontrar um destes vários erros do Oracle quando a sintaxe de nomenclatura está incorreta ou não está configurada corretamente:

* ORA-12154: TNS: não foi possível resolver o identificador de conexão especificado.
* ORA-12514: o ouvinte TNS no momento não sabe sobre o serviço solicitado no descritor de conexão.
* ORA-12541: TNS: nenhum ouvinte.
* ORA-12170: TNS: ocorrência de tempo limite de conexão.
* ORA-12504: O ouvinte TNS não recebeu SERVICE_NAME em CONNECT_DATA.

Esses erros poderão ocorrer se o cliente Oracle não estiver instalado ou não estiver configurado corretamente. Se ele estiver instalado, verifique se o arquivo tnsnames.ora está configurado corretamente e se você está usando o net_service_name adequado. Você também precisará garantir que o net_service_name seja o mesmo entre o computador que está usando o Power BI Desktop e o computador que está executando o gateway. Para obter mais informações, consulte [Instalando o cliente Oracle](#install-the-oracle-client).

Também poderá ocorrer um problema de compatibilidade entre a versão do servidor Oracle e a versão do Oracle Data Access Client. Normalmente, o ideal é que essas versões sejam correspondentes, pois algumas combinações são incompatíveis. Por exemplo, o ODAC 12.x não dá suporte ao Oracle Server versão 9.

Se você baixou o Power BI Desktop da Microsoft Store, talvez não possa se conectar aos bancos de dados Oracle devido a um problema de driver do Oracle. Se esse problema ocorrer, a mensagem de erro retornada será: *Referência de objeto não definida*. Para resolver o problema, siga uma destas etapas:

* Baixe o Power BI Desktop no [Centro de Download](https://www.microsoft.com/download/details.aspx?id=58494) em vez da Microsoft Store.

* Caso deseje usar a versão da Microsoft Store: no computador local, copie oraons.dll de _12.X.X\client_X_ para _12.X.X\client_X\bin_, em que _X_ representa os números de versão e diretório.

Se a mensagem de erro *Referência de objeto não definida* for exibida, no Power BI Gateway, quando você se conectar a um banco de dados Oracle, siga as instruções descritas em [Gerenciar sua fonte de dados: Oracle](service-gateway-onprem-manage-oracle.md).

Se você estiver usando o Servidor de Relatórios do Power BI, confira as diretrizes do artigo [Tipo de conexão Oracle](https://docs.microsoft.com/sql/reporting-services/report-data/oracle-connection-type-ssrs?view=sql-server-ver15).
