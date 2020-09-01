---
title: Criar conteúdo para migrar para o Power BI
description: Diretrizes sobre como criar e validar conteúdo ao migrar para o Power BI.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/20/2020
ms.author: v-pemyer
ms.openlocfilehash: a12a320b061967e9201e3513e504277a9df586b4
ms.sourcegitcommit: 84e75a2cd92f4ba4e0c08ba296b981b79d6d0e82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88803122"
---
# <a name="createcontenttomigratetopowerbi"></a>Criar conteúdo para migrar para o Power BI

Este artigo descreve o **Estágio 4**, que trata da criação e da validação de conteúdo ao migrar para o Power BI.

:::image type="content" source="media/powerbi-migration-create-validate-content/migrate-to-powerbi-stage-4.png" alt-text="Imagem mostrando os estágios de uma migração para o Power BI. O Estágio 4 é enfatizado neste artigo.":::

> [!NOTE]
> Para obter uma explicação completa do gráfico acima, confira [Visão geral da migração para o Power BI](powerbi-migration-overview.md).

O foco do Estágio 4 é executar o trabalho real para converter a POC (prova de conceito) em uma solução pronta para produção.

A saída deste estágio é uma solução do Power BI validada em um workspace de desenvolvimento e pronta para implantação em produção.

> [!TIP]
> A maioria dos tópicos discutidos neste artigo também se aplica a um projeto de implementação padrão do Power BI.

## <a name="create-the-production-solution"></a>Criar a solução de produção

Neste momento, a mesma pessoa que realizou a POC pode continuar com a produção da solução do Power BI pronta para produção. Também é possível envolver outra pessoa. Se as linhas do tempo não forem comprometidas, é ótimo envolver pessoas que serão responsáveis pelo desenvolvimento do Power BI no futuro. Dessa forma, eles podem aprender ativamente.

> [!IMPORTANT]
> Reutilize o máximo possível do trabalho da POC.

### <a name="develop-new-import-dataset"></a>Desenvolver novo conjunto de dados de importação

Você pode optar por criar um conjunto de dados de Importação quando ainda não houver um conjunto de dados do Power BI para atender às suas necessidades ou ele não puder ser aprimorado para atender às suas necessidades.

Idealmente, desde o início, considere desacoplar o trabalho de desenvolvimento para dados e relatórios. [Desacoplar dados e relatórios](report-separate-from-model.md) facilitará a separação do trabalho e das permissões quando pessoas diferentes forem responsáveis pela modelagem de dados e relatórios. Isso gera uma abordagem mais escalonável e incentiva a reutilização de dados.

As atividades essenciais relacionadas ao desenvolvimento de um conjunto de dados de Importação incluem:

- [Adquirir dados](../connect-data/desktop-quickstart-connect-to-data.md) de uma ou mais fontes de dados (que podem ser um fluxo de dados do Power BI).
- [Moldar, combinar e preparar](../connect-data/desktop-shape-and-combine-data.md) dados.
- Criar o [modelo de conjunto de dados](../transform-model/desktop-modeling-view.md), incluindo [tabelas de datas](../transform-model/desktop-date-tables.md).
- Criar e verificar [relações de modelo](../transform-model/desktop-create-and-manage-relationships.md).
- Definir [medidas](../transform-model/desktop-measures.md).
- Configurar [segurança em nível de linha](../admin/service-admin-rls.md), se necessário.
- Configurar sinônimos e [otimizar P e R](../natural-language/q-and-a-best-practices.md).
- Planeje a escalabilidade, o desempenho e a simultaneidade, que podem influenciar suas decisões sobre modos de armazenamento de dados, como usar um [modelo composto](../transform-model/desktop-composite-models.md) ou [agregações](../transform-model/desktop-aggregations.md).

> [!TIP]
> Se você tiver diferentes ambientes de desenvolvimento/teste/produção, considere [criar parâmetros](/power-query/power-query-query-parameters) para fontes de dados. Isso tornará a implantação, descrita no [Estágio 5](powerbi-migration-deploy-support-monitor.md), significativamente mais fácil.

### <a name="develop-new-reports-and-dashboards"></a>Desenvolver novos relatórios e dashboards

As atividades essenciais relacionadas ao desenvolvimento de um relatório ou dashboard do Power BI incluem:

- Decidir usar uma conexão dinâmica com um modelo de dados existente ou criar um modelo de dados
- Ao criar um modelo de dados, decida sobre o [modo de armazenamento de dados](../transform-model/desktop-storage-mode.md) para tabelas de modelo (Importação, DirectQuery ou Composto).
- Decida sobre a melhor ferramenta de visualização de dados para atender aos requisitos: Power BI Desktop, Paginated Report Builder ou Excel.
- Decida sobre os [melhores visuais](../consumer/end-user-visual-type.md) para informar a história que o relatório precisa contar e abordar as perguntas que o relatório precisa responder.
- Garanta que todos os visuais apresentem terminologia clara, concisa e amigável para os negócios.
- Atenda aos requisitos de interatividade.
- Ao usar a conexão dinâmica, adicione [medidas no nível de relatório](../transform-model/desktop-tutorial-create-measures.md).
- Crie um [dashboard](../create-reports/service-dashboards.md) no serviço do Power BI, especialmente quando os consumidores quiserem um modo fácil de monitorar métricas-chave.

> [!NOTE]
> Muitas dessas decisões terão sido tomadas em estágios anteriores do planejamento ou na POC técnica.

## <a name="validate-the-solution"></a>Validar a solução

Há quatro aspectos principais para a validação de uma solução do Power BI:

1. Precisão de dados
2. Segurança
3. Funcionalidade
4. Desempenho

### <a name="validate-data-accuracy"></a>Validar a precisão dos dados

Como um esforço único durante a migração, você precisará garantir que os dados no novo relatório correspondam ao que é exibido no relatório herdado. Se houver uma diferença, você deve poder explicar o porquê. É mais comum do que você pode imaginar encontrar um erro na solução herdada que é resolvido na nova solução.

Como parte dos esforços de validação de dados contínuos, o novo relatório normalmente precisará ser verificado de maneira cruzada com o sistema de origem original. O ideal é que essa validação ocorra de modo repetido sempre que você publicar uma alteração no relatório.

### <a name="validate-security"></a>Validar a segurança

Ao validar a segurança, há dois aspectos principais a serem considerados:

- Permissões de dados
- Acesso a conjuntos de dados, relatórios e dashboards

Em um conjunto de dados de Importação, as permissões de dados são aplicadas definindo RLS ([segurança em nível de linha](../admin/service-admin-rls.md)). Também é possível que as permissões de dados sejam impostas pelo sistema de origem usando o modo de armazenamento DirectQuery (possivelmente com [logon único](../connect-data/service-gateway-sso-overview.md)).

As principais maneiras de permitir acesso ao conteúdo do Power BI são:

- [Funções do workspace](../collaborate-share/service-new-workspaces.md#roles-in-the-new-workspaces) (para editores e visualizadores de conteúdo).
- [Permissões de aplicativo](../collaborate-share/service-create-distribute-apps.md#publish-your-app) aplicadas a um conjunto empacotado de conteúdo do workspace (para visualizadores).
- [Compartilhar](../collaborate-share/service-share-dashboards.md) um relatório ou dashboard individual (para visualizadores).

> [!TIP]
> É recomendável treinar os autores de conteúdo sobre como gerenciar a segurança com eficiência. Também é importante ter testes, auditoria e monitoramento robustos em vigor.

### <a name="validate-functionality"></a>Validar a funcionalidade

É o momento de verificar novamente os detalhes do conjunto de dados, como nomes de campo, formatação, classificação e comportamento de resumo padrão. Recursos de relatório interativos, como [segmentações](../visuals/power-bi-visualization-slicers.md), [busca detalhada](../consumer/end-user-drill.md), [detalhamento](../create-reports/desktop-drillthrough.md), [expressões](../create-reports/desktop-conditional-format-visual-titles.md), [botões](../create-reports/desktop-buttons.md) ou [indicadores](../create-reports/desktop-bookmarks.md), devem ser verificados também.

Durante o processo de desenvolvimento, a solução do Power BI deve ser publicada em um workspace de desenvolvimento no serviço do Power BI regularmente. Verifique se todas as funcionalidades funcionam conforme o esperado no serviço, como a renderização de visuais personalizados. Também é um bom momento para fazer testes adicionais. Teste [atualização agendada](../connect-data/refresh-scheduled-refresh.md), [P e R](../consumer/end-user-q-and-a.md) e como os relatórios e dashboards examinam um [dispositivo móvel](../consumer/mobile/mobile-apps-for-mobile-devices.md).

### <a name="validate-performance"></a>Validar o desempenho

O desempenho da solução do Power BI é importante para a experiência do consumidor. A maioria dos relatórios deve apresentar visuais em menos de 10 segundos. Se você tiver relatórios que levam mais tempo para carregar, pause e reconsidere o que pode estar contribuindo para os atrasos. O desempenho do relatório deve ser avaliado regularmente no serviço do Power BI, além de no Power BI Desktop.

Muitos problemas de desempenho baixo [DAX (Data Analysis eXpressions)](../transform-model/desktop-quickstart-learn-dax-basics.md), design ruim do conjunto de dados ou design de relatório de baixa qualidade (por exemplo, tentar renderizar muitos elementos visuais em uma única página). Problemas de ambiente técnico, como rede, gateway de dados sobrecarregado ou como uma capacidade Premium é configurada, também podem contribuir para problemas de desempenho. Para obter mais informações, confira [Guia de otimização para o Power BI](power-bi-optimization.md) e [Solucionar problemas de desempenho de relatório no Power BI](report-performance-troubleshoot.md).

## <a name="document-the-solution"></a>Documentar a solução

Há dois tipos principais de documentação úteis para uma solução do Power BI:

- Documentação do conjunto de dados
- Documentação do relatório

A documentação pode ser armazenada em qualquer lugar de fácil acesso pelo público-alvo. As opções comuns incluem:

- **Um site do SharePoint:** um site do SharePoint pode existir para seu centro de excelência ou um site interno da comunidade do Power BI.
- **Um aplicativo:** as URLs podem ser configuradas ao publicar um aplicativo do Power BI para direcionar o consumidor a mais informações.
- **Arquivos do Power BI Desktop individuais:** elementos de modelo, como tabelas e colunas, podem definir uma descrição. Essas descrições aparecem como dicas de ferramentas no painel **Campos** ao criar relatórios.

> [!TIP]
> Se você criar um site para servir como um hub para a documentação relacionada ao Power BI, considere [personalizar o menu Obter Ajuda](../admin/service-admin-portal.md#publish-get-help-information) com seu local de URL.

### <a name="create-dataset-documentation"></a>Criar documentação de conjunto de dados

A documentação do conjunto de dados é direcionada aos usuários que gerenciarão o conjunto de dados um no futuro. É útil incluir:

- Decisões de design tomadas e os motivos.
- Quem é o proprietário, realiza a manutenção e certifica conjuntos de dados.
- Requisitos de atualização de dados.
- Regras de negócios personalizadas definidas em conjuntos de dados.
- Segurança de conjunto de dados específico ou requisitos de privacidade de dados.
- Necessidades de manutenção futuras.
- Problemas conhecidos abertos ou itens da lista de pendências adiados.

Você também pode optar por criar um log de alterações que resume as alterações mais importantes que aconteceram ao conjunto de dados ao longo do tempo.

### <a name="create-report-documentation"></a>Criar documentação do relatório

A documentação do relatório, que normalmente é estruturada como orientada a consumidores de relatório, pode ajudar os consumidores a obter mais valor dos relatórios e dashboards. Um breve tutorial em vídeo muitas vezes funciona bem.

Você também pode optar por incluir a documentação adicional do relatório em uma página oculta do relatório. Ela pode incluir decisões de design e um log de alterações.

## <a name="next-steps"></a>Próximas etapas

No [próximo artigo desta série sobre migração do Power BI](powerbi-migration-deploy-support-monitor.md), saiba mais sobre o Estágio 5, que trata da implantação, do suporte e do monitoramento do conteúdo ao migrar para o Power BI.

Outros recursos úteis incluem:

- [Transformação de BI da Microsoft](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [White paper de Planejamento de uma implantação empresarial do Power BI](https://aka.ms/PBIEnterpriseDeploymentWP)
- Dúvidas? [Experimente perguntar à Comunidade do Power BI](https://community.powerbi.com/)
- Sugestões? [Contribuir com ideias para aprimorar o Power BI](https://ideas.powerbi.com/)

Parceiros experientes do Power BI estão disponíveis para ajudar sua organização a alcançar sucesso no processo de migração. Para envolver um parceiro do Power BI, visite o [portal de parceiro de Power BI](https://powerbi.microsoft.com/partners/).
