---
title: Visão geral dos pipelines de implantação
description: Saiba o que são os pipelines de implantação no Power BI
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-service
ms.date: 09/09/2020
ms.openlocfilehash: 3994a5cdad4d80c87d4153ffe57af685d7a21d36
ms.sourcegitcommit: 92b033ee7a6e36808371b247b7b41536cee6c2f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "90008573"
---
# <a name="introduction-to-deployment-pipelines-preview"></a>Introdução aos pipelines de implantação (versão prévia)

No mundo atual, a análise é uma parte vital da tomada de decisões em quase todas as organizações. O uso crescente do Power BI como uma ferramenta de análise exige que ele use mais dados, seja atrativo e fácil de usar. E, acima de tudo, o Power BI precisa estar sempre disponível e ser confiável. Para atender a esses requisitos, os criadores do BI devem colaborar com eficiência.

A ferramenta pipelines de implantação permite que os criadores de BI gerenciem o ciclo de vida do conteúdo organizacional. A ferramenta é eficiente e reutilizável para criadores em uma empresa com capacidade Premium. A ferramenta permite que os criadores desenvolvam e testem o conteúdo do Power BI antes que o conteúdo seja consumido pelos usuários. Os tipos de conteúdo incluem relatórios, dashboards e conjuntos de dados.

A ferramenta é projetada como um pipeline com três estágios:

* **<a name="development"></a>Desenvolvimento**
    
    Esse estágio é usado para projetar, criar e carregar novos conteúdos com outros criadores. É o primeiro estágio em pipelines de implantação.

* **<a name="test"></a>Teste**

    Você está pronto para entrar no estágio de teste depois de fazer todas as alterações no conteúdo. Você carregará o conteúdo modificado, de modo que ele possa ser movido para esse estágio de teste. Veja três exemplos do que pode ser feito no ambiente de teste:

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
