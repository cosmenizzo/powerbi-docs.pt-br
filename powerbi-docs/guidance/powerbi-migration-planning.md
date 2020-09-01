---
title: Planejar a implantação para migrar para o Power BI
description: Diretrizes sobre como planejar a implantação ao migrar para o Power BI.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/20/2020
ms.author: v-pemyer
ms.openlocfilehash: 590e28c727cab88b008d7a05e7df22244e8dabf0
ms.sourcegitcommit: 84e75a2cd92f4ba4e0c08ba296b981b79d6d0e82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88803103"
---
# <a name="plandeploymenttomigratetopowerbi"></a>Planejar a implantação para migrar para o Power BI

Este artigo descreve o **Estágio 2**, que trata do planejamento da migração para uma única solução do Power BI.

:::image type="content" source="media/powerbi-migration-planning/migrate-to-powerbi-stage-2.png" alt-text="Imagem mostrando os estágios de uma migração para o Power BI. O Estágio 2 é enfatizado neste artigo.":::

> [!NOTE]
> Para obter uma explicação completa do gráfico acima, confira [Visão geral da migração para o Power BI](powerbi-migration-overview.md).

O foco do Estágio 2 é definir como os requisitos definidos no Estágio 1 são usados para migrar uma solução para o Power BI.

A saída do Estágio 2 inclui o máximo possível de decisões específicas para guiar o processo de implantação.

A tomada de decisões dessa natureza é um processo iterativo e não linear. Algum planejamento já terá ocorrido nas [etapas pré-migração](powerbi-migration-pre-migration-steps.md). O aprendizado de uma prova de conceito (descrito no [Estágio 3](powerbi-migration-proof-of-concept.md)) pode ocorrer em paralelo com o planejamento da implantação. Mesmo durante a criação da solução (descrita no [Estágio 4](powerbi-migration-create-validate-content.md)), podem surgir informações adicionais que influenciam as decisões de implantação.

> [!IMPORTANT]
> Os Estágios de 1 a 5 representam atividades relacionadas a uma solução específica. Há decisões e atividades no nível organizacional/do locatário que afetam o processo no nível da solução. Algumas dessas atividades de planejamento de alto nível são discutidas no artigo [Visão geral da migração para o Power BI](powerbi-migration-overview.md). Quando apropriado, adie as decisões de nível organizacional quanto à eficiência e à consistência.

> [!TIP]
> A maioria dos tópicos discutidos neste artigo também se aplicam a um projeto de implementação de Power BI padrão.

## <a name="choose-power-bi-product"></a>Escolher o produto do Power BI

Uma das primeiras decisões é escolher o produto do Power BI. É uma decisão entre o [serviço do Power BI](../fundamentals/power-bi-service-overview.md) ou o [Servidor de Relatórios do Power BI](../report-server/get-started.md). Depois que o conteúdo tiver sido publicado, muitas opções adicionais ficarão disponíveis, como inserção, entrega móvel e assinaturas de email.

Para obter mais informações sobre considerações de arquitetura, consulte a **Seção 3** do [whitepaper Como planejar uma implantação empresarial do Power BI](https://aka.ms/PBIEnterpriseDeploymentWP).

> [!CAUTION]
> Se você estiver tentado a depender do uso de arquivos do Power BI Desktop armazenados em um sistema de arquivos, lembre-se de que essa não é a abordagem ideal. O uso do serviço do Power BI (ou Servidor de Relatórios do Power BI) tem vantagens significativas em termos de segurança, distribuição de conteúdo e colaboração. A capacidade de auditar e monitorar atividades também é habilitada pelo serviço do Power BI.

## <a name="decide-on-workspace-management-approach"></a>Decidir sobre a abordagem de gerenciamento de workspace

Os [workspaces](../collaborate-share/service-new-workspaces.md) são um conceito fundamental do serviço do Power BI, o que torna o gerenciamento do workspace um aspecto importante do planejamento. As perguntas a serem feitas incluem:

- É necessário um novo workspace para essa nova solução?
- Serão necessários workspaces separados para acomodar o desenvolvimento, o teste e a produção?
- Serão usados workspaces separados para dados e relatórios ou um único workspace será suficiente? Ter workspaces separados têm várias vantagens, especialmente para proteger conjuntos de dados. Quando necessário, eles podem ser gerenciados separadamente dos usuários que publicam relatórios.
- Quais são os requisitos de segurança para o workspace? Ele influencia o planejamento de [funções de workspace](../collaborate-share/service-new-workspaces.md#roles-in-the-new-workspaces). Se um aplicativo for usado por consumidores de conteúdo, [permissões para o aplicativo](../collaborate-share/service-create-distribute-apps.md#publish-your-app) serão gerenciadas separadamente do workspace. Permissões distintas para visualizadores de aplicativos permitem flexibilidade adicional para atender aos requisitos de segurança para consumidores somente leitura de relatórios ou dashboards.
- Os grupos existentes podem ser usados para proteger o novo conteúdo? Há suporte para os grupos do Azure Active Directory e do Microsoft 365. Quando alinhado com os processos existentes, usar grupos torna o gerenciamento de permissões mais fácil do que usando atribuições a usuários individuais.
- Há considerações de segurança relacionadas a usuários convidados externos? Talvez seja necessário trabalhar com o administrador do Azure Active Directory e o administrador do Power BI para configurar o [acesso do usuário convidado](../admin/service-admin-azure-ad-b2b.md).

> [!TIP]
> Considere criar um workspace para uma atividade ou projeto de negócios específico. Você pode estar tentado a começar a estruturar workspaces trabalho com base em sua estrutura organizacional (como um workspace por departamento), mas essa abordagem acaba sendo muito ampla.

## <a name="determine-how-content-will-be-consumed"></a>Determinar como o conteúdo será consumido

É útil entender como os consumidores de uma solução preferem exibir relatórios e dashboards. As perguntas a serem feitas incluem:

- Um [aplicativo do Power BI](../consumer/end-user-apps.md) (que consiste em relatórios e dashboards de um workspace) é a melhor maneira de fornecer conteúdo aos consumidores ou o acesso direto a um workspace é suficiente para os visualizadores de conteúdo?
- Determinados relatórios e dashboards serão inseridos em outro lugar, como [Teams](../collaborate-share/service-embed-report-microsoft-teams.md), [SharePoint Online](../collaborate-share/service-embed-report-spo.md) ou um [portal ou site seguro](../collaborate-share/service-embed-secure.md)?
- Os consumidores acessarão o conteúdo usando [dispositivos móveis](../consumer/mobile/mobile-apps-for-mobile-devices.md)? Os requisitos para entregar relatórios a dispositivos de fator forma pequeno influenciarão algumas [decisões de design de relatório](../create-reports/desktop-create-phone-report.md).

## <a name="decide-if-other-content-may-be-created"></a>Decida se outro conteúdo pode ser criado

Há várias decisões importantes a serem feitas com relação a permitir que os consumidores criem novos conteúdos, como:

- Os consumidores terão permissão para criar novos relatórios usando conjunto de dados um publicado? Essa funcionalidade pode ser habilitada atribuindo o conjunto de dados de [permissão de build](../connect-data/service-datasets-build-permissions.md) a um usuário.
- Se os consumidores desejarem personalizar um relatório, eles poderão [salvar uma cópia](../connect-data/service-datasets-copy-reports.md) e personalizá-la para atender às suas necessidades?

> [!CAUTION]
> Embora a funcionalidade _Salvar uma cópia_ seja um recurso útil, ela deve ser usada com cautela quando o relatório inclui determinadas mensagens gráficas ou de cabeçalho/rodapé. Como os logotipos, ícones e mensagens textuais muitas vezes estão relacionados a requisitos de identidade visual ou conformidade regulatória, é importante controlar cuidadosamente como eles são entregues e distribuídos. Se _Salvar uma cópia_ for usado, mas as mensagens gráficas ou de cabeçalho/rodapé originais permanecerem inalteradas pelo novo autor, isso poderá resultar em confusão sobre quem produziu de fato o relatório. Também pode reduzir o significado da identidade visual.

## <a name="evaluate-needs-for-premium-capacity"></a>Avaliar as necessidades da capacidade Premium

Funcionalidades adicionais estão disponíveis quando um workspace é armazenado em uma [capacidade Premium](../admin/service-premium-what-is.md). Aqui estão várias razões pelas quais os workspaces na capacidade Premium podem ser vantajosos:

- O conteúdo pode ser acessado por consumidores que não têm uma licença do Power BI Pro.
- Suporte para grandes conjuntos de dados.
- Suporte para atualizações de dados mais frequentes.
- Suporte para o uso do conjunto completo de recursos de fluxos de dados.
- Recursos corporativos, incluindo pipelines de implantação e o ponto de extremidade XMLA.
- Suporte para relatórios paginados (quando a carga de trabalho está habilitada).

## <a name="determine-data-acquisition-method"></a>Determinar método de aquisição de dados

Os dados exigidos por um relatório podem influenciar várias decisões. As perguntas a serem feitas incluem:

- É possível usar um [conjunto de dados compartilhado](../connect-data/service-datasets-share.md) do Power BI ou é adequado criar um conjunto de dados do Power BI para essa solução?
- Um conjunto de dados compartilhado precisa ser ampliado com novos dados ou medidas para atender às necessidades adicionais?
- Qual [modo de armazenamento de dados](../transform-model/desktop-storage-mode.md) será mais apropriado? As opções incluem Importação, DirectQuery, Composto ou Conexão Dinâmica.
- [Agregações](../transform-model/desktop-aggregations.md) devem ser usadas para aprimorar o desempenho da consulta?
- A criação de um [fluxo de dados](../transform-model/service-dataflows-overview.md) será útil e pode servir como fonte para vários conjuntos de valores?
- Uma nova [fonte de dados do gateway](../connect-data/service-gateway-data-sources.md) precisa ser registrada?

## <a name="decide-where-original-content-will-be-stored"></a>Decida em que local o conteúdo original será armazenado

Além de planejar o destino de implantação de destino, também é importante planejar em que local o conteúdo original (ou fonte) será armazenado, como:

- Especifique um local aprovado para armazenar os arquivos originais do Power BI Desktop (.pbix). O ideal é que esse local esteja disponível apenas para pessoas que editem o conteúdo. Ele deve estar alinhado com a maneira como a segurança é configurada no serviço do Power BI.
- Use um local para os arquivos originais do Power BI Desktop que incluam o histórico de controle do código-fonte ou de versão. O controle de versão permite que o autor do conteúdo reverta para uma versão anterior do arquivo, se necessário. O OneDrive for Business ou o SharePoint funciona bem para essa finalidade.
- Especifique um local aprovado para armazenar dados de origem não centralizados, como arquivos simples ou arquivos do Excel. Deve ser um caminho que qualquer um dos autores do conjunto de dados pode acessar sem erros e cujo backup é feito regularmente.
- Especifique um local aprovado para o conteúdo exportado do serviço do Power BI. A meta é garantir que a segurança definida no serviço do Power BI não seja inadvertidamente contornada.

> [!IMPORTANT]
> Especificar um local protegido para arquivos originais do Power BI Desktop é particularmente importante quando eles contêm dados importados.

## <a name="assess-the-level-of-effort"></a>Avaliar o nível de esforço

Quando há informações suficientes disponíveis nos requisitos (que foram descritos no [Estágio 1](powerbi-migration-requirements.md)) e no processo de planejamento da implantação da solução, agora é possível avaliar o nível de esforço. Em seguida, é possível formular um plano de projeto com tarefas, linha do tempo e responsabilidade.

> [!TIP]
> Custos de mão de obra (salários e remunerações) geralmente estão entre as despesas mais altas na maioria das organizações. Embora possa ser difícil de estimar com precisão, aprimoramentos de produtividade têm um excelente ROI (retorno sobre o investimento).

## <a name="next-steps"></a>Próximas etapas

No [próximo artigo desta série sobre migração do Power BI](powerbi-migration-proof-of-concept.md), saiba mais sobre o Estágio 3, que trata da condução de uma prova de conceito para mitigar o risco e lidar o mais cedo possível com itens desconhecidos ao migrar para o Power BI.

Outros recursos úteis incluem:

- [Transformação de BI da Microsoft](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [White paper de Planejamento de uma implantação empresarial do Power BI](https://aka.ms/PBIEnterpriseDeploymentWP)
- Dúvidas? [Experimente perguntar à Comunidade do Power BI](https://community.powerbi.com/)
- Sugestões? [Contribuir com ideias para aprimorar o Power BI](https://ideas.powerbi.com/)

Parceiros experientes do Power BI estão disponíveis para ajudar sua organização a alcançar sucesso no processo de migração. Para envolver um parceiro do Power BI, visite o [portal de parceiro de Power BI](https://powerbi.microsoft.com/partners/).
