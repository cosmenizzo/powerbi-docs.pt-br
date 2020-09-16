---
title: arquivo de inclusão
description: arquivo de inclusão
services: powerbi
author: davidiseminger
ms.service: powerbi
ms.topic: include
ms.date: 04/28/2020
ms.author: davidi
ms.openlocfilehash: ed87101fe7f5fadd24594d53bbd0ffb6f029faa4
ms.sourcegitcommit: 92b033ee7a6e36808371b247b7b41536cee6c2f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "90012858"
---
## <a name="single-sign-on"></a>Logon único

Depois de publicar um conjunto de dados DirectQuery do SQL do Azure no serviço, você poderá habilitar o SSO (logon único) usando o OAuth2 do Azure AD (Azure Active Directory) para os usuários finais.

Para habilitar o SSO, acesse as configurações para o conjunto de dados, abra a guia **Fontes de dados** e marque a caixa SSO.

![Configure as caixa de diálogo DQ do SQL do Azure](media/direct-query-sso/sso-dialog.png)

Quando a opção de SSO está habilitada e os usuários acessam os relatórios baseados na fonte de dados, o Power BI envia suas credenciais autenticadas do Azure AD nas consultas ao banco de dados SQL do Azure ou ao data warehouse. Com essa opção, o Power BI pode respeitar as configurações de segurança definidas no nível da fonte de dados.

A opção de SSO entra em vigor em todos os conjuntos de dados que usam essa fonte de dados. Isso não afeta o método de autenticação usado para cenários de importação.

> [!Note]
> Não há suporte para Autenticação Multifator do Microsoft Azure (MFA). Os usuários que desejam usar o SSO com o DirectQuery precisam ser isentos de MFA.
