---
title: Usar chaves gerenciadas pelo cliente no Power BI
description: Saiba como usar chaves gerenciadas pelo cliente no Power BI.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.date: 08/12/2020
LocalizationGroup: Premium
ms.openlocfilehash: 8d13cc7a24486fada7f8d428ba52abeaa49d2518
ms.sourcegitcommit: b60063c49ac39f8b28c448908ecbb44b54326335
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "88160915"
---
# <a name="use-customer-managed-keys-in-power-bi"></a>Usar chaves gerenciadas pelo cliente no Power BI

Power BI criptografa dados em repouso e em andamento. Por padrão, o Power BI usa chaves gerenciadas pela Microsoft para criptografar seus dados. As organizações podem optar por usar chaves próprias para a criptografia do conteúdo do usuário em repouso no Power BI, de imagens de relatórios a conjuntos de dados importados em capacidades Premium. 

## <a name="why-use-customer-managed-keys"></a>Por que usar chaves gerenciadas pelo cliente
Com a CMK (chaves gerenciadas pelo cliente) do Power BI, as organizações podem atender aos requisitos de conformidade para a criptografia de dados em repouso com um provedor de serviços de nuvem próprio (neste caso, a Microsoft). A CMK permite que as organizações criptografem o conteúdo do usuário do Power BI usando uma chave elas fornecem e gerenciam. Revogar uma chave gerenciada pelo cliente torna o conteúdo do usuário ilegível no Power BI para todos, incluindo a Microsoft, durante uma hora. Em comparação com a oferta do BYOK, a CMK também abrange o conteúdo do usuário fora das capacidades do Power BI Premium, além de aplicar políticas de cache mais rígidas e, por padrão, habilitar o BYOK em todas as capacidades. 
 
## <a name="how-to-use-customer-managed-keys"></a>Como usar chaves gerenciadas pelo cliente
Para aceitar as chaves gerenciadas pelo cliente do Power BI, sua organização deverá atender aos requisitos de tamanho. O administrador global da organização deve enviar uma solicitação de suporte à Microsoft. Ou ele pode entrar em contato com o gerente de conta Microsoft da organização para saber mais sobre o processo.  


## <a name="next-steps"></a>Próximas etapas

Os seguintes links fornecem informações que podem ser úteis para obter as chaves gerenciadas pelo cliente:

* [Criptografia BYOK (Bring Your Own Key) para o Power BI](service-encryption-byok.md)
* [Configurar o suporte Multi-Geo para o Power BI Premium](service-admin-premium-multi-geo.md)
* [Como as capacidades funcionam](service-premium-what-is.md#how-capacities-function)
* [Atualização incremental](service-premium-incremental-refresh.md).
