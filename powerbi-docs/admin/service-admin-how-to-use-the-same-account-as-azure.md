---
title: Usando a mesma conta para Power BI e o Azure
description: Como usar o mesmo logon de conta para o Power BI e o Azure
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Troubleshooting
ms.openlocfilehash: fe93fa3f41cf1c340b31ce3c6f817f842f3039ff
ms.sourcegitcommit: c18130ea61e67ba111be870ddb971c6413a4b632
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86161642"
---
# <a name="using-the-same-account-for-power-bi-and-azure"></a>Usando a mesma conta para Power BI e o Azure

Se você for um usuário do Power BI e do Azure, convém usar o mesmo logon para ambos os serviços para que nãos seja preciso digitar sua senha duas vezes.

O Power BI conecta você com sua conta institucional, associada ao seu endereço de email de trabalho ou da escola.  O Azure conecta você com uma conta da Microsoft ou conta organizacional.

Se você deseja usar o mesmo logon para o Azure e o Power BI, certifique-se de entrar no Azure com sua conta organizacional.

**E se eu já tiver entrado no Azure com minha conta da Microsoft?**

Você pode adicionar sua conta organizacional como um coadministrador no Azure seguindo estas etapas:

1. Entre no [portal do Azure](https://portal.azure.com/). Se você for um usuário em vários diretórios do Azure, selecione **Assinaturas** e filtre para exibir somente o diretório e as assinaturas que deseja editar.

1. No painel de navegação, selecione **Controle de acesso (IAM)** e, em seguida, selecione **Adicionar** \> **Adicionar coadministrador**.

    ![Captura de tela do Controle de acesso com a opção Adicionar um coadministrador em destaque.](media/service-admin-how-to-use-the-same-account-as-azure/add-co-administrator.png)

1. Digite o endereço de email associado à sua conta organizacional e selecione **Adicionar**.

1. Da próxima vez que você entrar no portal do Azure, use seu endereço de email organizacional.

Mais perguntas? [Experimente a Comunidade do Power BI](https://community.powerbi.com/)
