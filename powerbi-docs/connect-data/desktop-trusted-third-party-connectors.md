---
title: Conectores de Terceiros Confiáveis no Power BI
description: Como confiar em um conector de terceiros assinado no Power BI
author: cpopell
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/3/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 06b117a271671092a94aa8e7994269344b444178
ms.sourcegitcommit: 9350f994b7f18b0a52a2e9f8f8f8e472c342ea42
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90859602"
---
# <a name="trusted-third-party-connectors"></a>Conectores de terceiros confiáveis

## <a name="why-do-you-need-trusted-third-party-connectors"></a>Por que você precisa de conectores de terceiros confiáveis?

No Power BI, geralmente recomendamos manter seu nível "Segurança da extensão de dados" no nível mais alto, o que impede o carregamento de código não certificado pela Microsoft. No entanto, pode haver muitos casos em que você queira carregar conectores específicos – os que você escreveu ou aqueles fornecidos a você por um consultor ou fornecedor fora do caminho de certificação da Microsoft.

O desenvolvedor de um determinado conector pode assiná-lo com um certificado e fornecer as informações de que você precisa para carregá-lo de maneira segura sem reduzir as configurações de segurança.

Se desejar saber mais sobre as configurações de segurança, você poderá ler sobre elas [aqui](./desktop-connector-extensibility.md).

## <a name="using-the-registry-to-trust-third-party-connectors"></a>Usar o Registro para confiar em conectores de terceiros

Confiar em conectores de terceiros no Power BI é feito listando a impressão digital do certificado em que você deseja confiar em um valor de registro especificado. Se essa impressão digital coincidir com a do certificado no conector que você deseja carregar, você poderá carregá-la no nível de segurança "Recomendado" do Power BI. 

O caminho do Registro é HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Power BI Desktop. Verifique se o caminho existe ou crie-o. Escolhemos esse local por ele ser controlado principalmente pela política de TI, além de exigir acesso de administração de computador local para edição. 

![Registro do Power BI Desktop sem um conjunto de chaves de terceiros confiáveis](media/desktop-trusted-third-party-connectors/desktoptrustedthird1.png)

Adicione um novo valor no caminho especificado acima. O tipo deve ser "Valor de Cadeia de Caracteres Múltipla" (REG_MULTI_SZ) e deve ser chamado "TrustedCertificateThumbprints" 

![O Registro do Power BI Desktop com uma entrada para conectores de terceiros confiáveis, mas sem chaves](media/desktop-trusted-third-party-connectors/desktoptrustedthird2.png)

Adicione as impressões digitais dos certificados em que você deseja confiar. Você pode adicionar vários certificados usando "\0" como um delimitador ou, no editor do Registro, clique com o botão direito do mouse -> modifique e coloque cada impressão digital em uma nova linha. A impressão digital de exemplo é obtida de um certificado autoassinado. 

 ![O Registro do Power BI Desktop com um conjunto de chaves de terceiros confiáveis](media/desktop-trusted-third-party-connectors/desktoptrustedthird3.png)

Se você tiver seguido as instruções adequadamente e recebido a impressão digital adequada do seu desenvolvedor, agora você deverá poder configurar conectores assinados com o certificado associado.

## <a name="how-to-sign-connectors"></a>Como assinar conectores

Se você tiver um conector ou um desenvolvedor precisar assinar, poderá ler sobre isso nos documentos do Power Query [aqui](/power-query/handlingconnectorsigning).