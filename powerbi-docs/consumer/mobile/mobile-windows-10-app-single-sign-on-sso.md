---
title: O logon único no aplicativo móvel do Windows do Power BI
description: Leia sobre SSO (Logon Único) no aplicativo móvel do Windows do Power BI. SSO significa que você acessa todos os aplicativos e recursos necessários para fazer negócios entrando apenas uma vez com uma única conta de usuário.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 03/11/2020
ms.author: painbar
ms.openlocfilehash: 4202d2c7e4c87f8085a04af9922cf7cc6c55fbfd
ms.sourcegitcommit: 9350f994b7f18b0a52a2e9f8f8f8e472c342ea42
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90860177"
---
# <a name="single-sign-on-in-the-power-bi-mobile-windows-app"></a>O logon único no aplicativo móvel do Windows do Power BI

Leia sobre SSO (Logon Único) no aplicativo móvel do Windows do Power BI. SSO significa que você acessa todos os aplicativos e recursos necessários para fazer negócios entrando apenas uma vez com uma única conta de usuário. Quando você estiver conectado, poderá acessar todos esses aplicativos sem precisar se autenticar novamente. 

Porque o aplicativo do Windows do Power BI está integrado ao Azure Active Directory, você pode usar suas contas organizacionais primárias não apenas para entrar em seus dispositivos ingressados no domínio, mas também para entrar no serviço do Power BI. Se você estiver exibindo o Power BI no telefone Windows, verifique se a conta usada para o Power BI está configurada como corporativa ou de estudante conta nas configurações do dispositivo.  

SSO é habilitado somente para dispositivos Windows gerenciados pelo Microsoft Azure Active Directory.

>[!NOTE]
>O suporte de aplicativo móvel Power BI para **telefones que usam o Windows 10 Mobile** será descontinuado em 16 de março de 2021. [Saiba mais](/legal/powerbi/powerbi-mobile/power-bi-mobile-app-end-of-support-for-windows-phones)

## <a name="sign-in-with-sso"></a>Entrar com SSO

Para simplificar o processo de conexão, quando você instala o aplicativo pela primeira vez, o aplicativo automaticamente tenta autenticar-se no serviço do Power BI usando SSO. Somente se esse processo não tiver êxito o aplicativo solicitará que você forneça suas credenciais para o Power BI.  

Se você já estiver usando o aplicativo móvel do Power BI para Windows, ao atualizar para a nova versão do aplicativo, também poderá usar SSO. Saia do aplicativo, feche-o e reabra-o. Quando o aplicativo é reaberto, ele tenta automaticamente usar suas credenciais atuais do Windows para autenticar-se no serviço do Power BI. 

Se você prefere não usar suas credenciais da sessão ativa atual do Windows para entrar no Power BI, basta ir até **Configurações**, sair e entrar com credenciais diferentes. 
 
## <a name="next-steps"></a>Próximas etapas

- [Introdução ao aplicativo móvel do Power BI para Windows 10](mobile-windows-10-phone-app-get-started.md)
- Perguntas? [Experimente perguntar à Comunidade do Power BI](https://community.powerbi.com/)