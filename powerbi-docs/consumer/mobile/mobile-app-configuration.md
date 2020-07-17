---
title: Definições de configuração de aplicativos do Power BI
description: Como personalizar o comportamento do Power BI usando a ferramenta de MDM
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 07/14/2020
ms.author: painbar
ms.openlocfilehash: f9b6efd07aad3d2058e49f81ae21095b618123ee
ms.sourcegitcommit: d8acf2fb0318708a3e8e1e259cb3747b0312b312
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86385919"
---
# <a name="remotely-configure-power-bi-app-using-mobile-device-management-mdm-tool"></a>Configurar remotamente o aplicativo do Power BI usando a ferramenta de MDM (gerenciamento de dispositivo móvel)

O aplicativo Power BI Mobile para iOS e Android dá suporte a configurações que permitem aos administradores de serviços de MDM (gerenciamento de dispositivo móvel), como o Intune, personalizar o comportamento do aplicativo.

O aplicativo Power BI Mobile é compatível com os cenários de configuração a seguir:

* Configuração de Servidor de Relatório (iOS e Android)
* Configurações de proteção de dados (iOS e Android)
* Desabilitar logon único (iOS e Android)
* Configurações de interação (iOS e Android)

## <a name="report-server-configuration-ios-and-android"></a>Configuração de Servidor de Relatório (iOS e Android)

O aplicativo Power BI para iOS e Android permite aos administradores efetuar push remotamente da configuração do Servidor de Relatório para os dispositivos registrados.

| Chave | Type | Descrição |
|---|---|---|
| com.microsoft.powerbi.mobile.ServerURL | String | URL do Servidor de Relatório.<br><br>Deve começar com http/https.|
| com.microsoft.powerbi.mobile.ServerUsername | String | [opcional]<br><br>O nome de usuário a ser usado para conectar o servidor.<br><br>Se não existir, o aplicativo solicitará ao usuário que digite o nome de usuário para a conexão.|
| com.microsoft.powerbi.mobile.ServerDisplayName | String | [opcional]<br><br>O valor padrão é "Servidor de relatório"<br><br>Um nome amigável usado no aplicativo para representar o servidor. |
| com.microsoft.powerbi.mobile.OverrideServerDetails | Boolean | [opcional]<br><br>O valor padrão é True. Quando definido como True, substituirá qualquer definição do Servidor de Relatório que já estiver no dispositivo móvel. Os servidores existentes que já estão configurados serão excluídos. Substituir a definição para True também evita que o usuário remova essa configuração.<br><br>Se definido como False, adicionará os valores enviados por push, mantendo as configurações atuais. Se a mesma URL do servidor já estiver configurada no aplicativo móvel, o aplicativo deixará essa configuração como está. O aplicativo não solicita ao usuário para se autenticar novamente no mesmo servidor. |

## <a name="data-protection-settings-ios-and-android"></a>Configurações de proteção de dados (iOS e Android)

O aplicativo móvel do Power BI para iOS e Android oferece aos administradores a capacidade de personalizar a configuração padrão de acordo com as configurações de segurança e privacidade. No iOS, você pode forçar os usuários a fornecer o Face ID, o Touch ID ou uma senha ao acessarem o aplicativo móvel do Power BI. No Android, você pode forçar os usuários a usar a autenticação biométrica (ID da Impressão Digital).

| Chave | Type | Descrição |
|---|---|---|
| com.microsoft.powerbi.mobile.ForceDeviceAuthentication | Boolean | O valor padrão é Falso. <br><br>A biometria, como o Touch ID ou o Face ID (iOS) ou a ID da Impressão Digital (Android), pode ser necessária para que os usuários acessem o aplicativo nos próprios dispositivos. Quando for necessária, a biometria será usada, além da autenticação.<br><br>Se você está usando políticas de proteção de aplicativo, a Microsoft recomenda desabilitar essa configuração para evitar duplo prompt de acesso. |

>[!NOTE]
>As configurações de proteção de dados serão aplicadas somente aos dispositivos Android que dão suporte à autenticação biométrica.

## <a name="disable-single-sign-on-ios-and-android"></a>Desabilitar logon único (iOS e Android)

Por padrão, o aplicativo móvel do Power BI fornece uma experiência conveniente de logon único para um usuário individual, minimizando o número de vezes que ele precisa fornecer um nome de usuário e uma senha. Esse comportamento de logon único se baseia na suposição de que o dispositivo é o dispositivo pessoal do usuário e que há apenas um usuário que usa o dispositivo e os aplicativos contidos nele.

Os administradores podem ativar a configuração **DisableSingleSignOn** no arquivo de configuração do aplicativo para configurar remotamente o aplicativo a fim de desabilitar o logon único e solicitar explicitamente a senha do usuário durante a entrada.

Essa é uma configuração somente de administrador que é feita por meio da configuração remota. O usuário final não pode alterá-la.

| Chave | Type | Descrição |
|---|---|---|
| com.microsoft.powerbi.mobile.DisableSingleSignOn | Boolean | O valor padrão é Falso.<br><br>Depois que um usuário se desconectar, o aplicativo não reutilizará as credenciais existentes, mas solicitará ao próximo usuário que forneça uma senha para se autenticar e se conectar ao serviço do Power BI.
 |

## <a name="interaction-settings-ios-and-android"></a>Configurações de interação (iOS e Android)

O aplicativo Power BI para iOS e Android oferecerá aos administradores a capacidade de definir configurações de interação se for decidido que as configurações de interação padrão precisam ser alteradas em grupos de usuários em uma organização.

>[!NOTE]
>Atualmente, nem todas as interações têm suporte em todos os dispositivos. Confira [Definir configurações de interação de relatório](mobile-app-interaction-settings.md) para obter um gráfico que mostra a disponibilidade atual entre os dispositivos.

| Chave | Type | Valores | Descrição |
|---|---|---|---|
| com.microsoft.powerbi.mobile.ReportTapInteraction | String |  <nobr>toque simples</nobr><br><nobr>toque duplo</nobr> | Configure se um toque no visual também fará uma seleção de ponto de dados. |
| com.microsoft.powerbi.mobile.EnableMultiSelect | Boolean |  <nobr>Verdadeiro</nobr><br><nobr>Falso</nobr> | Configure se um toque em um ponto de dados substituirá a seleção atual ou será adicionado à seleção atual. |
| com.microsoft.powerbi.mobile.RefreshAction | String |  <nobr>deslizar para atualizar</nobr><br>botão | Configure se o usuário terá um botão para atualizar o relatório ou deverá usar o recurso "deslizar para atualizar". |
| com.microsoft.powerbi.mobile.FooterAppearance | String |  encaixado<br>dinâmico | Configure se o rodapé do relatório será encaixado na parte inferior do relatório ou ocultado automaticamente. |

## <a name="deploying-app-configuration-settings"></a>Implantando definições de configuração de aplicativos

Veja a seguir as etapas necessárias para criar uma política de configuração de aplicativo. Depois de criar a política de configuração, você pode atribuir suas configurações a grupos de usuários.

1. Conecte a ferramenta MDM.
2. Crie e nomeie uma nova política de configuração do aplicativo.
3. Escolha os usuários para os quais essa política de configuração de aplicativo será distribuída.
4. Crie pares de chave-valor para a configuração que você deseja enviar por push aos usuários.

O portal do Intune permite aos administradores implantar facilmente essas configurações no aplicativo do Power BI por meio de políticas de configuração de aplicativos. No entanto, qualquer provedor de MDM é compatível. Se você não estiver usando o Intune, precisará consultar a documentação de MDM sobre como implantar essas configurações.

## <a name="next-steps"></a>Próximas etapas

* Obtenha o aplicativo móvel do Power BI na [App Store](https://apps.apple.com/app/microsoft-power-bi/id929738808) e no [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.powerbim&amp;amp;clcid=0x409)
* Siga [@MSPowerBI no Twitter](https://twitter.com/MSPowerBI)
* Participe da conversa na [Comunidade do Power BI](https://community.powerbi.com/)