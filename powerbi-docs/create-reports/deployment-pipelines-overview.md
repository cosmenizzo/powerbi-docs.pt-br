---
title: Visão geral dos pipelines de implantação
description: Saiba o que são os pipelines de implantação no Power BI
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-service
ms.date: 05/06/2020
ms.openlocfilehash: 5522d84cab235270a2eb368be02cfa0fb4e5eaa9
ms.sourcegitcommit: 10c5b6cd5e7070f96de8a9f1d9b95f3d242ac7f2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2020
ms.locfileid: "86557131"
---
# <a name="introduction-to-deployment-pipelines-preview"></a>Introdução aos pipelines de implantação (versão prévia)

No mundo atual, a análise é uma parte vital da tomada de decisões em quase todas as organizações. O uso crescente do Power BI como uma ferramenta de análise exige que ele use mais dados, seja atrativo e fácil de usar. E, acima de tudo, o Power BI precisa estar sempre disponível e ser confiável. Para atender a esses requisitos, os criadores do BI devem colaborar com eficiência.

Os pipelines de implantação são uma ferramenta eficiente e reutilizável que permite que os criadores do BI em uma empresa com capacidade Premium gerenciem o ciclo de vida do conteúdo organizacional. Isso permite desenvolver e testar o conteúdo do Power BI, como relatórios, dashboards e conjuntos de dados, antes que eles sejam consumidos pelos usuários finais.

A ferramenta é projetada como um pipeline com três estágios:

* **<a name="development"></a>Desenvolvimento**
    
    Esse estágio é usado para projetar, criar e carregar novos conteúdos com outros criadores. É o primeiro estágio em pipelines de implantação.

* **<a name="test"></a>Teste**

    Depois que o conteúdo é carregado e todas as alterações são feitas no estágio de desenvolvimento, o conteúdo pode ser movido para este estágio para teste. Aqui estão três exemplos do que pode ser feito no ambiente de teste:

    * Compartilhar conteúdo com testadores e revisores

    * Carregar e executar testes com grandes volumes de dados

    * Testar seu aplicativo para ver como ele será exibido aos usuários finais

* **<a name="production"></a>Produção**

    Depois de testar o conteúdo, use o estágio de produção para compartilhar a versão final do seu conteúdo com os usuários empresariais em toda a organização.

![Uma captura de tela de um pipeline de implantação em funcionamento, com todos os três estágios (implantação, teste e produção) preenchidos.](media/deployment-pipelines-overview/deployment-pipelines.png)

## <a name="next-steps"></a>Próximas etapas

>[!div class="nextstepaction"]
>[Introdução aos pipelines de implantação](deployment-pipelines-get-started.md)

>[!div class="nextstepaction"]
>[Compreender o processo de pipelines de implantação](deployment-pipelines-process.md)

>[!div class="nextstepaction"]
>[Solução de problemas de pipelines de implantação](deployment-pipelines-troubleshooting.md)

>[!div class="nextstepaction"]
>[Melhores práticas para pipelines de implantação](deployment-pipelines-best-practices.md)