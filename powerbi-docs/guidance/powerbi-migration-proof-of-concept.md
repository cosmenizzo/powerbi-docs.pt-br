---
title: Realizar prova de conceito para migrar para o Power BI
description: Diretrizes sobre a condução de uma prova de conceito ao migrar para o Power BI.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/20/2020
ms.author: v-pemyer
ms.openlocfilehash: a7b7a848aafc3a581c1a19cf34366d61ba891f86
ms.sourcegitcommit: 84e75a2cd92f4ba4e0c08ba296b981b79d6d0e82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88803102"
---
# <a name="conductproofofconcepttomigratetopowerbi"></a>Realizar prova de conceito para migrar para o Power BI

Este artigo descreve o **Estágio 3**, que trata da condução de uma POC (prova de conceito) para atenuar o risco e lidar o mais cedo possível com itens desconhecidos ao migrar para o Power BI.

:::image type="content" source="media/powerbi-migration-proof-of-concept/migrate-to-powerbi-stage-3.png" alt-text="Imagem mostrando os estágios de uma migração para o Power BI. O Estágio 3 é enfatizado neste artigo.":::

> [!NOTE]
> Para obter uma explicação completa do gráfico acima, confira [Visão geral da migração para o Power BI](powerbi-migration-overview.md).

O foco do Estágio 3 é abordar elementos desconhecidos e mitigar riscos o mais cedo possível. Uma POC técnica é útil para validar suposições. Isso pode ser feito de modo iterativo junto com o planejamento da implantação da solução (descrito no [Estágio 2](powerbi-migration-planning.md)).

A saída desse Estágio é uma solução do Power BI com escopo restrito que aborda as perguntas iniciais abertas e está pronta para trabalho adicional no [Estágio 4](powerbi-migration-create-validate-content.md) para torná-lo pronto para produção.

> [!IMPORTANT]
> Não pretendemos que a POC seja um trabalho descartável. Em vez disso, esperamos que seja uma iteração inicial da solução pronta para produção. Na sua organização, você pode se referir a essa atividade como um protótipo, um piloto, uma maquete, um início rápido ou um MVP (produto minimamente viável). Nem sempre é necessário realizar uma POC e ela pode até mesmo ocorrer informalmente.

> [!TIP]
> A maioria dos tópicos discutidos neste artigo também se aplica a um projeto de implementação padrão do Power BI. À medida que sua organização adquire experiência com o Power BI, a necessidade de realizar POCs diminui. No entanto, devido ao rápido ritmo de versões com o Power BI e à introdução contínua dos novos recursos, você pode realizar regularmente POCs técnicas para fins de aprendizado.

## <a name="set-poc-goals-and-scope"></a>Definir metas e escopo da POC

Ao realizar uma POC, concentre-se nas seguintes metas:

- Verificar suas suposições sobre como um recurso funciona.
- Instruir-se sobre as diferenças em como o Power BI funciona em comparação à plataforma de BI herdada.
- Valide os entendimentos iniciais de determinados requisitos com especialistas no assunto.
- Crie um pequeno conjunto de dados contendo dados reais para entender e detectar quaisquer problemas com a estrutura de dados, as relações, os tipos de dados ou os valores de dados.
- Experimente e valide expressões da [sintaxe DAX](/dax/) usadas por cálculos de modelo.
- Teste a conectividade da fonte de dados usando um gateway (se for o gateway de origem).
- Testar a atualizar dados usando um gateway (se for um gateway de origem).
- Verifique as configurações de segurança, incluindo a segurança em nível de linha, quando aplicável.
- Experimente com decisões de layout e estéticas.
- Verifique se todas as funcionalidades no serviço do Power BI funcionam conforme o esperado.

O escopo da POC depende de quais são os itens desconhecidos ou quais metas precisam ser validadas com colegas. Para reduzir a complexidade, mantenha uma POC o mais limitada possível em termos de escopo.

Geralmente, com uma migração, os requisitos são bem conhecidos, pois há uma solução existente para começar. No entanto, dependendo da extensão das melhorias a serem feitas ou das habilidades em Power BI existentes, uma POC ainda fornece um valor significativo. Além disso, a rápida avaliação de protótipo com comentários do consumidor pode ser apropriada para esclarecer rapidamente os requisitos, especialmente se forem feitas melhorias.

> [!IMPORTANT]
> Mesmo que uma POC inclua apenas um subconjunto de dados ou inclua apenas visuais limitados, é muito importante levá-la do início ao fim. Ou seja, do desenvolvimento no Power BI Desktop à implantação em um workspace de desenvolvimento no serviço do Power BI. É a única maneira de atingir completamente os objetivos de POC. Isso é particularmente verdadeiro quando o serviço do Power BI deve fornecer funcionalidade crítica que você não usou antes, como um conjunto de dados do DirectQuery usando logon único. Durante a POC, concentre seus esforços em aspectos dos quais você não tem certeza ou que precisa verificar com outras pessoas.

## <a name="handle-differences-in-power-bi"></a>Lidar com as diferenças no Power BI

O Power BI pode ser usado como uma _ferramenta baseada em modelo_ ou como _ferramenta baseada em relatório_. Uma solução baseada em modelo envolve o desenvolvimento de um modelo de dados, enquanto uma solução baseada em relatório conecta-se a um modelo de dados já implantado.

Devido à sua extrema flexibilidade, há alguns aspectos sobre o Power BI que podem ser fundamentalmente diferentes da plataforma do BI herdada da qual você está migrando.

### <a name="consider-redesigning-the-data-architecture"></a>Considere a possibilidade de reformular a arquitetura de dados

Se você estiver migrando de uma plataforma do BI herdada que tenha a própria camada semântica, criar um conjunto de dados de Importação provavelmente será uma boa opção. O Power BI funciona melhor com um design de tabela no [esquema estrela](star-schema.md). Portanto, se a camada semântica herdada não for um esquema em estrela, talvez seja necessária alguma reformulação para aproveitar totalmente o Power BI. Esforçar-se para definir uma camada semântica que cumpre os princípios de design de esquema em estrela (incluindo relações, medidas usadas com frequência e terminologia organizacional amigável) é um excelente ponto de partida para autores de relatórios por autoatendimento.

Se você estiver migrando de uma plataforma de BI herdada na qual os relatórios fazem referência a fontes de dados relacionais usando consultas SQL ou procedimentos armazenados e estiver planejando usar o Power BI no modo [DirectQuery](../connect-data/desktop-use-directquery.md), poderá conseguir uma migração quase de um para um do modelo de dados.

> [!CAUTION]
> Se você vir a criação de muitos arquivos do Power BI Desktop incluindo uma única tabela importada, isso geralmente é um indício de que o design não é ideal. Caso você perceba essa situação, investigue se o uso de [conjuntos de dados compartilhados](../connect-data/service-datasets-across-workspaces.md) criados usando um design de [esquema em estrela](star-schema.md) poderia obter um resultado melhor.

### <a name="decide-how-to-handle-dashboard-conversions"></a>Decidir como lidar com conversões de dashboard

No setor de BI, um dashboard é uma coleção de visuais que exibem as principais métricas em uma única página. No entanto, no Power BI, um dashboard representa um recurso de visualização específico que só pode ser criado no serviço do Power BI. Ao migrar um dashboard de uma plataforma de BI herdada, você tem duas opções:

1. O dashboard herdado pode ser recriado como um _relatório_ do Power BI. A maioria dos relatórios é criada com o Power BI Desktop. Relatórios paginados e relatórios do Excel também são opções alternativas.
2. O dashboard herdado pode ser recriado como um _dashboard_ do Power BI. Os [dashboards](../fundamentals/service-basic-concepts.md#dashboards) são um recurso de visualização do serviço do Power BI. Os visuais de dashboard geralmente são criados fixando visuais de um ou mais relatórios, P e R ou Insights Rápidos.

> [!TIP]
> Como os dashboards são um tipo de conteúdo do Power BI, evite usar a palavra _dashboard_ no nome do relatório ou do dashboard.

### <a name="focus-on-the-big-picture-when-recreating-visuals"></a>Concentre-se na visão geral ao recriar elementos visuais

Cada ferramenta do BI tem seus pontos fortes e áreas de foco. Assim, os visuais de relatório exatos dos quais você dependia em uma plataforma do BI herdada podem não ter um equivalente próximo no Power BI.

Ao recriar visuais de relatório, concentre-se mais nas questões de negócio gerais que estão sendo abordadas pelo relatório. Isso elimina a pressão de replicar o design de cada visual exatamente da mesma maneira. Embora os consumidores de conteúdo gostem de consistência ao usar relatórios migrados, é importante não se deixar levar por debates demorados sobre pequenos detalhes.

## <a name="next-steps"></a>Próximas etapas

No [próximo artigo desta série sobre migração do Power BI](powerbi-migration-create-validate-content.md), saiba mais sobre o Estágio 4, que trata da criação e da validação de conteúdo ao migrar para o Power BI.

Outros recursos úteis incluem:

- [Transformação de BI da Microsoft](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [White paper de Planejamento de uma implantação empresarial do Power BI](https://aka.ms/PBIEnterpriseDeploymentWP)
- Dúvidas? [Experimente perguntar à Comunidade do Power BI](https://community.powerbi.com/)
- Sugestões? [Contribuir com ideias para aprimorar o Power BI](https://ideas.powerbi.com/)

Parceiros experientes do Power BI estão disponíveis para ajudar sua organização a alcançar sucesso no processo de migração. Para envolver um parceiro do Power BI, visite o [portal de parceiro de Power BI](https://powerbi.microsoft.com/partners/).
