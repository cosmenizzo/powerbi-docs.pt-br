---
title: Links privados para acessar o Power BI
description: Como configurar um link privado para usar o Power BI
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.author: davidi
ms.date: 09/14/2020
ms.custom: ''
LocalizationGroup: Administration
ms.openlocfilehash: 612fa923f45b427cb9c4fea4ecc1b18ad8580004
ms.sourcegitcommit: 376ea86f69545444f975378cbf63e54c2f75faa3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90084020"
---
# <a name="private-links-for-accessing-power-bi"></a>Links privados para acessar o Power BI

No Power BI, você pode configurar e usar um ponto de extremidade que permita que a sua organização acesse o Power BI em modo privado. Para configurar links privados, você precisa ser um administrador do Power BI e ter permissões no Azure para criar e configurar recursos como VMs (Máquinas Virtuais) e VNets (Redes Virtuais). 

As etapas que permitem acessar o Power BI com segurança em links privados são:

1. [Habilitar links privados para o Power BI](#enable-private-links-for-power-bi)
2. [Criar um recurso do Power BI no portal do Azure](#create-a-power-bi-resource-in-the-azure-portal)
3. [Criar uma rede virtual](#create-a-virtual-network)
4. [Criar uma VM (máquina virtual)](#create-a-virtual-machine-vm)
5. [Criar um ponto de extremidade privado](#create-a-private-endpoint)
6. [Conectar-se a uma VM usando a RDP (Área de Trabalho Remota)](#connect-to-a-vm-using-remote-desktop-rdp)
7. [Acessar o Power BI na máquina virtual em modo privado](#access-power-bi-privately-from-the-vm)
8. [Desabilitar o acesso público para o Power BI](#disable-public-access-for-power-bi)

As seções a seguir fornecem mais informações sobre cada etapa.

## <a name="enable-private-links-for-power-bi"></a>Habilitar links privados para o Power BI

Para começar, faça logon no Power BI em app.powerbi.com como administrador e navegue até o portal de administração. Selecione **Configurações de locatário** e role a página até **Rede Avançada**. Em seguida, alterne o botão de opção para ativar o **Link Privado do Azure**, conforme mostrado na imagem a seguir. 

A configuração de um link privado para o seu locatário leva aproximadamente 15 minutos, que inclui a configuração de um FQDN separado para o locatário, a fim de se comunicar com os serviços do Power BI em modo privado.

![Ativar o Link Privado do Azure](media/service-security-private-links/service-private-links-01.png)

Depois de concluir essa etapa, vá para a próxima.

## <a name="create-a-power-bi-resource-in-the-azure-portal"></a>Criar um recurso do Power BI no portal do Azure

Em seguida, entre no [portal do Azure](https://portal.azure.com) e crie um recurso do Power BI usando um **Modelo do Azure**. Substitua os parâmetros do exemplo de modelo do ARM, mostrados na tabela a seguir, para criar um recurso do Power BI.


|**Parâmetro**  |**Valor**  |
|---------|---------|
|```<resource-name>```    | myPowerBIResource         |
|```<tenant-object-id>```     | 52d40f65-ad6d-48c3-906f-1ccf598612d4         |

Criar um modelo do ARM 

```
{
  "$schema": "http://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
  "contentVersion": "1.0.0.0",
  "parameters": {},
  "resources": [
      {
          "type":"Microsoft.PowerBI/privateLinkServicesForPowerBI",
          "apiVersion": "2020-06-01",
          "name" : "<resource-name>",
          "location": "global",
          "properties" : 
          {
               "tenantId": "<tenant-object-id>"
          }
      }
  ]
}
```

Na caixa de diálogo exibida, marque a caixa de seleção para concordar com os termos e condições e selecione **Comprar**.

![Concorde com os termos e condições e adquira o modelo](media/service-security-private-links/service-private-links-02.png)


## <a name="create-a-virtual-network"></a>Criar uma rede virtual

A próxima etapa será criar uma rede virtual e uma sub-rede. Substitua os parâmetros de exemplo da tabela abaixo por parâmetros próprios para criar uma rede virtual e uma sub-rede.

| Parâmetro |   Valor| 
|---------|---------|
| ```<resource-group-name>```   | myResourceGroup |
| ```<virtual-network-name>```  | myVirtualNetwork |
| ```<region-name>```   | Centro dos EUA  |
| ```<IPv4-address-space>```    | 10.1.0.0/16 |
| ```<subnet-name>```   | mySubnet |
| ```<subnet-address-range>```  | 10.1.0.0/24 |

1. No canto superior esquerdo da tela, selecione **Criar um recurso > Rede > Rede virtual** ou pesquise por **Rede virtual** na caixa de pesquisa.
2. Em **Criar rede virtual**, insira ou selecione as seguintes informações na guia **Informações Básicas**:

    |Configurações | Valor |
    |-------------------|---------|
    |**Detalhes do projeto**|
    |Subscription | Selecionar sua Assinatura do Azure |
    |Grupo de recursos |   Selecione **Criar**, insira ```<resource-group-name>```, escolha **OK** ou um ```<resource-group-name>``` existente com base nos parâmetros. |
    |**Detalhes da instância** |
    | Nome  | Inserir ```<virtual-network-name>``` |
    |Region | Selecione ```<region-name>``` |
    
    A imagem a seguir mostra a guia **Informações Básicas**.
    
    ![Criar uma rede virtual, guia Informações Básicas](media/service-security-private-links/service-private-links-03.png)


3. Depois, selecione a guia **Endereços IP** ou o botão **Avançar: Endereços IP** na parte inferior do formulário. Na guia Endereços IP, insira as seguintes informações:

    |Configurações | Valor |
    |-------------------|---------|
    |Espaço de endereço IPv4 |Inserir ```<IPv4-address-space>``` |
    
    ![Criar uma rede virtual, guia Endereços IP](media/service-security-private-links/service-private-links-04.png)
    

4. Em **Nome da sub-rede** escolha a palavra *padrão* e, em **Editar sub-rede**, insira as seguintes informações:

    |Configurações | Valor |
    |-------------------|---------|
    | Nome da sub-rede |Inserir ```<subnet-name>``` |
    | Intervalo de endereços da sub-rede | Inserir ```<subnet-address-range>``` |
    
    
    ![Criar uma rede virtual, guia Editar sub-rede](media/service-security-private-links/service-private-links-05.png)

5. Depois, selecione **Salvar** e escolha a guia **Examinar + criar** ou o botão **Examinar + criar**. 

6. Em seguida, selecione **Criar**.

Depois de concluir essas etapas, você poderá criar uma VM (máquina virtual), conforme descrito na próxima seção.

## <a name="create-a-virtual-machine-vm"></a>Criar uma VM (máquina virtual)


A próxima etapa será criar uma rede virtual e a sub-rede para hospedar a VM (máquina virtual).

1. No canto superior esquerdo da tela no portal do Azure, selecione **Criar um recurso > Computação > Máquina Virtual**.

2. Em **Criar uma máquina virtual – Informações Básicas**, insira ou selecione as seguintes informações:

    |Configurações | Valor |
    |-------------------|---------|
    |**Detalhes do projeto**||
    |Subscription | Selecionar sua Assinatura do Azure |
    |Grupo de recursos |   Selecione **myResourceGroup**, criado na seção anterior. |
    |**Detalhes da instância** ||
    |Nome | Insira **myVm** |
    |Region | Selecione **EUA Central** |
    |Opções de disponibilidade| Mantenha o padrão **Nenhuma redundância de infraestrutura necessária** |
    |Imagem | Selecione **Windows 10 Pro** |
    |Tamanho | Mantenha o padrão **Standard DS1 v2** |
    |CONTA DE ADMINISTRADOR ||
    |Nome de usuário |Insira um nome de usuário de sua escolha |
    |Senha | Insira uma senha de sua escolha. A senha precisa ter, no mínimo, 12 caracteres e atender aos [requisitos de complexidade definidos](https://docs.microsoft.com/azure/virtual-machines/windows/faq?toc=/azure/virtual-network/toc.json#what-are-the-password-requirements-when-creating-a-vm) |
    |Confirmar Senha | Insira novamente a senha |
    |REGRAS DE PORTA DE ENTRADA ||
    |Porta de entrada públicas | Mantenha o padrão **Nenhum** |
    |ECONOMIZAR DINHEIRO ||
    |Já tem uma licença do Windows? |  Mantenha o padrão **Não** |

3. Em seguida, selecione **Avançar: Discos**
4. Em **Criar uma máquina virtual – Discos**, mantenha os padrões e selecione **Avançar: Rede**.
5. Em **Criar uma máquina virtual – Rede**, selecione as seguintes informações:

    |Configurações | Valor |
    |-------------------|---------|
    |Rede virtual|   Mantenha o padrão **MyVirtualNetwork**|
    |Espaço de endereço| Mantenha o padrão **10.1.0.0/24**|
    |Sub-rede |Mantenha o padrão **mySubnet (10.1.0.0/24)**|
    |IP público| Mantenha o padrão **(nova) myVm-ip**|
    |Porta de entrada públicas|  Selecione **Permitir selecionadas**|
    |Selecione as portas de entrada|  Selecione **RDP**|

6. Selecione **Examinar + criar**. Você é levado até a página **Examinar + criar**, na qual o Azure valida sua configuração.
7. Quando vir a mensagem **Validação aprovada**, selecione **Criar**.


## <a name="create-a-private-endpoint"></a>Criar um ponto de extremidade privado

A próxima etapa, que é descrita nesta seção, será criar um ponto de extremidade privado para o Power BI.

1. No canto superior esquerdo da tela no portal do Azure, selecione **Criar um recurso > Rede > Central do Link Privado (Versão Prévia)** .
2. Em **Central do Link Privado – Visão Geral**, na opção **Criar uma conexão privada com um serviço**, selecione **Criar ponto de extremidade privado**.
3. Em **Criar um ponto de extremidade privado (Versão Prévia) – Informações Básicas**, insira ou selecione as seguintes informações:

    |Configurações | Valor |
    |-------------------|---------|
    |**Detalhes do projeto** ||
    |Subscription|  Selecionar sua Assinatura do Azure|
    |Grupo de recursos|    Selecione **myResourceGroup**. Você o criou na seção anterior|
    |**Detalhes da instância** ||
    |Nome|  Insira *myPrivateEndpoint*. Se esse nome já estiver sendo usado, crie um nome exclusivo|
    |Region|    Selecione **EUA Central**|
    
    A imagem a seguir mostra a janela **Criar um ponto de extremidade privado – Informações Básicas**.
    
    ![Criar um ponto de extremidade privado, informações básicas](media/service-security-private-links/service-private-links-06.png)

4. Depois que as informações forem concluídas, selecione **Avançar: Recurso** e na página **Criar um ponto de extremidade privado – Recurso**, insira ou selecione as seguintes informações:

    |Configurações | Valor |
    |-------------------|---------|
    |Método de conexão| Selecione Conectar-se a um recurso do Azure em meu diretório|
    |Assinatura|  Selecionar sua assinatura|
    |Tipo de recurso| Selecione **Microsoft.PowerBI/privateLinkServicesForPowerBI** |
    |Recurso|  myPowerBIResource|
    |Sub-recurso de destino|   Locatário|
    
    A imagem a seguir mostra a janela **Criar um ponto de extremidade privado – Recurso**.
    
    ![Criar um ponto de extremidade privado, recurso](media/service-security-private-links/service-private-links-07.png)

5. Depois que as informações forem inseridas corretamente, selecione **Avançar: Configuração**, e em **Criar um ponto de extremidade privado (Versão Prévia) – Configuração**, insira ou selecione as seguintes informações:

    |Configurações | Valor |
    |-------------------|---------|
    |**REDE** ||
    |Rede virtual|   Selecione *myVirtualNetwork* |
    |Sub-rede |Selecione *mySubnet* |
    |**INTEGRAÇÃO DE DNS PRIVADO** ||
    |Integrar com a zona DNS privado|   Selecione **Sim** |
    |Zona DNS privado   |Selecionar <br><br>
    *(Novo)privatelink.analysis.windows.net* <br>
    *(Novo)privatelink.pbidedicated.windows.net* <br>
    *(Novo)privatelink.tip1.powerquery.microsoft.com* |
    
    A imagem a seguir mostra a janela **Criar um ponto de extremidade privado – Configuração**.
    
    ![Criar um ponto de extremidade privado, configuração](media/service-security-private-links/service-private-links-08.png)
    
    Em seguida, selecione **Examinar + criar**, que exibe a página **Examinar + criar**, na qual o Azure valida sua configuração. Quando vir a mensagem **Validação aprovada**, selecione **Criar**.

## <a name="connect-to-a-vm-using-remote-desktop-rdp"></a>Conectar-se a uma VM usando a RDP (Área de Trabalho Remota)

Depois de criar sua máquina virtual, chamada **myVM**, conecte-se a ela na Internet usando as seguintes etapas:

1. Na barra de pesquisa do portal, insira *myVm*.
2. Selecione o botão **Conectar**. Depois que você selecionar o botão **Conectar**, a opção **Conectar-se à máquina virtual** será aberta.
3. Selecione **Baixar Arquivo RDP**. O Azure cria um arquivo .rdp (protocolo RDP) e ele é baixado no computador.
4. Abra o arquivo .rdp baixado.
5. Se solicitado, selecione **Conectar**.
6. Insira o nome de usuário e a senha que você especificou ao criar a VM na etapa anterior.
7. Selecione **OK**.
8. Você pode receber um aviso do certificado durante o processo de logon. Se você receber um aviso de certificado, selecione **Sim** ou **Continuar**.

## <a name="access-power-bi-privately-from-the-vm"></a>Acessar o Power BI na VM em modo privado

A próxima etapa será acessar o Power BI em modo privado na máquina virtual criada na etapa anterior usando as seguintes etapas: 

1. Na Área de Trabalho Remota do myVM, abra o PowerShell.
2. Insira nslookup 52d40f65ad6d48c3906f1ccf598612d4-api.privatelink.analysis.windows.net.
3. Você receberá uma mensagem semelhante a esta:

    ```
    Server:  UnKnown
    Address:  168.63.129.16
    
    Non-authoritative answer:
    Name:    52d40f65ad6d48c3906f1ccf598612d4-api.privatelink.analysis.windows.net
    Address:  10.1.0.4
    ```

4. Abra o navegador e acesse app.powerbi.com para acessar o Power BI em modo privado.

## <a name="disable-public-access-for-power-bi"></a>Desabilitar o acesso público para o Power BI

Por fim, você precisará desabilitar o acesso público para o Power BI. 

Faça logon em app.powerbi.com como administrador e navegue até o **portal de administração**. Selecione **Configurações de locatário** e role a página até a seção **Rede avançada**. Habilite o botão de alternância na seção **Bloquear o Acesso Público à Internet**, conforme mostrado na imagem a seguir. São necessários aproximadamente 15 minutos para que o sistema desabilite o acesso da sua organização ao Power BI na Internet pública.

Pronto! Depois que você seguir essas etapas, o Power BI só ficará acessível para suas organizações por meio de links privados, não podendo ser acessado na Internet pública. 

## <a name="considerations-and-limitations"></a>Considerações e limitações

Há algumas considerações para ter em mente ao trabalhar com os links privados no Power BI:

* Qualquer uso de imagens ou temas externos não estará disponível no uso de um ambiente de link privado, e isso poderá afetar os visuais personalizados
* Os serviços de exportação, como Exportar para PDF, a exportação para o Excel de um relatório e outros serviços de exportação não funcionam com o uso de um ambiente de link privado
* Os relatórios do SQL Server Reporting Services, geralmente conhecidos como arquivos RDL (arquivos de formato *.rdl), não são renderizados em ambientes de link privado


## <a name="next-steps"></a>Próximas etapas

- [Administração do Power BI em sua organização](service-admin-administering-power-bi-in-your-organization.md)  
- [Noções básicas sobre a função de administrador do Power BI](service-admin-role.md)  
- [Auditoria do Power BI em sua organização](service-admin-auditing.md)  

Mais perguntas? [Experimente perguntar à Comunidade do Power BI](https://community.powerbi.com/)
