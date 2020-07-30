---
title: Gerenciar sua fonte de dados – Oracle
description: Como gerenciar o gateway de dados local e as fontes de dados que pertencem ao gateway.
author: arthiriyer
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: how-to
ms.date: 07/15/2019
ms.author: arthii
LocalizationGroup: Gateways
ms.openlocfilehash: 0b617afdeb69f2367b83ad40b2146f5ce78cdc89
ms.sourcegitcommit: a254f6e2453656f6783690669be8e881934e15ac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87363998"
---
# <a name="manage-your-data-source---oracle"></a>Gerenciar sua fonte de dados – Oracle

[!INCLUDE [gateway-rewrite](../includes/gateway-rewrite.md)]

Depois de [instalar o gateway de dados local](/data-integration/gateway/service-gateway-install), será necessário [adicionar fontes de dados](service-gateway-data-sources.md#add-a-data-source) que possam ser usadas com o gateway. Este artigo aborda como trabalhar com gateways e fontes de dados Oracle para a atualização agendada ou para o DirectQuery.

## <a name="connect-to-an-oracle-database"></a>Conectar-se a um banco de dados Oracle
Para se conectar a um banco de dados Oracle com o gateway de dados local, o software cliente Oracle correto precisa estar instalado no computador que executa o gateway. O software cliente Oracle usado depende da versão do servidor Oracle, mas sempre corresponderá ao gateway de 64 bits.

Versões do Oracle com suporte: 
- Oracle Server 9 e posterior
- Software ODAC (Oracle Data Access Client) 11.2 e posterior

## <a name="install-the-oracle-client"></a>Instalar o cliente Oracle
- [baixar e instalar o cliente Oracle de 64 bits](https://www.oracle.com/database/technologies/odac-downloads.html).

> [!NOTE]
> Escolha uma versão do ODAC (Oracle Data Access Client) que seja compatível com o Oracle Server. Por exemplo, o ODAC 12.x nem sempre dá suporte ao Oracle Server versão 9.
> Escolha o Windows Installer do Oracle Client.
> Durante a instalação do cliente Oracle, habilite a opção *Configurar os provedores ODP.NET e/ou Oracle para ASP.NET em nível de computador* marcando a caixa de seleção correspondente durante o assistente de instalação. Algumas versões do assistente de cliente Oracle marcam a caixa de seleção por padrão, outras não. Verifique se a caixa de seleção está selecionada para que Power BI possa se conectar ao seu banco de dados Oracle.
 
Após o cliente ser instalado e o ODAC ser configurado corretamente, é recomendável usar o PowerBI Desktop ou outro cliente de teste para verificar a instalação e a configuração corretas no gateway.

## <a name="add-a-data-source"></a>Adicionar uma fonte de dados

Para obter mais informações sobre como adicionar uma fonte de dados, consulte [Adicionar uma fonte de dados](service-gateway-data-sources.md#add-a-data-source). Em **Tipo de Fonte de Dados**, selecione **Oracle**.

![Adicionar a fonte de dados Oracle](media/service-gateway-onprem-manage-oracle/data-source-oracle.png)

Depois de selecionar o tipo de fonte de dados Oracle, preencha as informações da fonte de dados, que incluem o **Servidor** e o **Banco de dados**. 

Em **Método de Autenticação**, você pode escolher **Windows** ou **Básico**. Escolha **Básico** se você planeja usar uma conta criada com a autenticação do Oracle em vez da autenticação do Windows. Em seguida, insira as credenciais que serão usadas para esta fonte de dados.

> [!NOTE]
> Todas as consultas à fonte de dados serão executadas com essas credenciais. Para saber mais sobre como as credenciais são armazenadas, confira [Armazenar credenciais criptografadas na nuvem](service-gateway-data-sources.md#store-encrypted-credentials-in-the-cloud).

![Preencher as configurações de fonte de dados](media/service-gateway-onprem-manage-oracle/data-source-oracle2.png)

Depois de preencher tudo, selecione **Adicionar**. Agora você pode usar esta fonte de dados para a atualização agendada ou para o DirectQuery, em relação a um servidor Oracle local. Você verá *Conexão Bem-sucedida* se tiver êxito.

![Exibindo o status da conexão](media/service-gateway-onprem-manage-oracle/datasourcesettings4.png)

### <a name="advanced-settings"></a>Configurações avançadas

Opcionalmente, você pode configurar o nível de privacidade para sua fonte de dados. Essa configuração controla como os dados podem ser combinados. Ela é usada somente para a atualização agendada. A configuração de nível de privacidade não se aplica ao DirectQuery. Para saber mais sobre os níveis de privacidade para sua fonte de dados, confira [Níveis de privacidade (Power Query)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Definir o nível de privacidade](media/service-gateway-onprem-manage-oracle/datasourcesettings9.png)

## <a name="use-the-data-source"></a>Usar a fonte de dados

Depois de criar a fonte de dados, ela está disponível para uso com as conexões do DirectQuery ou por meio da atualização agendada.

> [!WARNING]
> Os nomes do servidor e do banco de dados devem corresponder entre o Power BI Desktop e a fonte de dados no gateway de dados local.

O vínculo entre o conjunto de dados e a fonte de dados no gateway baseia-se nos nomes do servidor e do banco de dados. Esses nomes devem corresponder. Por exemplo, se você fornecer um endereço IP como nome do servidor no Power BI Desktop, precisará usar o endereço IP como fonte de dados na configuração do gateway. Esse nome também deve corresponder a um alias definido no arquivo tnsnames.ora. Para obter mais informações sobre o arquivo tnsnames.ora, consulte [Instalar o cliente Oracle](#install-the-oracle-client).

Esse requisito existe para o DirectQuery e para a atualização agendada.

### <a name="use-the-data-source-with-directquery-connections"></a>Usar a fonte de dados com conexões do DirectQuery

Verifique se os nomes do servidor e do banco de dados correspondem entre o Power BI Desktop e a fonte de dados configurada para o gateway. Para que seja possível publicar os conjuntos de dados do DirectQuery, você também precisa verificar se o usuário está listado na guia **Usuários** da fonte de dados. A seleção para o DirectQuery ocorre no Power BI Desktop quando você importa dados pela primeira vez. Para obter mais informações sobre como usar o DirectQuery, consulte [Usar o DirectQuery no Power BI Desktop](desktop-use-directquery.md).

Após a publicação, por meio do Power BI Desktop ou do recurso **Obter Dados**, seus relatórios deverão começar a funcionar. Pode levar vários minutos após a criação da fonte de dados no gateway para que a conexão seja utilizável.

### <a name="use-the-data-source-with-scheduled-refresh"></a>Usar a fonte de dados com a atualização agendada

Se estiver listado na guia **Usuários** da fonte de dados configurada no gateway e houver a correspondência entre os nomes do servidor e do banco de dados, você verá o gateway como uma opção a ser usada com a atualização agendada.

![Exibir os usuários](media/service-gateway-onprem-manage-oracle/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="troubleshooting"></a>Solução de problemas

Você pode encontrar um destes vários erros do Oracle quando a sintaxe de nomenclatura está incorreta ou não está configurada corretamente:

* ORA-12154: TNS: não foi possível resolver o identificador de conexão especificado.
* ORA-12514: o ouvinte TNS no momento não sabe sobre o serviço solicitado no descritor de conexão.
* ORA-12541: TNS: nenhum ouvinte.
* ORA-12170: TNS: ocorrência de tempo limite de conexão.
* ORA-12504: O ouvinte TNS não recebeu SERVICE_NAME em CONNECT_DATA.

Esses erros poderão ocorrer se o cliente Oracle não estiver instalado ou não estiver configurado corretamente. Se ele estiver instalado, verifique se o arquivo tnsnames.ora está configurado corretamente e se você está usando o net_service_name adequado. Você também precisará garantir que o net_service_name seja o mesmo entre o computador que está usando o Power BI Desktop e o computador que está executando o gateway. Para obter mais informações, consulte [Instalando o cliente Oracle](#install-the-oracle-client).

Também poderá ocorrer um problema de compatibilidade entre a versão do servidor Oracle e a versão do Oracle Data Access Client. Normalmente, o ideal é que essas versões sejam correspondentes, pois algumas combinações são incompatíveis. Por exemplo, o ODAC 12.x não dá suporte ao Oracle Server versão 9.

Para diagnosticar problemas de conectividade entre o servidor de fonte de dados e o computador do gateway, é recomendável instalar um cliente (como o PowerBI Desktop ou o Oracle ODBC Test) no computador do gateway. Use o cliente para verificar a conectividade com o servidor de fonte de dados.

Para obter informações adicionais de solução de problemas relativas ao gateway, veja [Solução de problemas do gateway de dados local](/data-integration/gateway/service-gateway-tshoot).

## <a name="next-steps"></a>Próximas etapas

* [Solucionar problemas de gateways – Power BI](service-gateway-onprem-tshoot.md)
* [Power BI Premium](../admin/service-premium-what-is.md)

Mais perguntas? Experimente perguntar à [Comunidade do Power BI](https://community.powerbi.com/).
