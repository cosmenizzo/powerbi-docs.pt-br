---
title: Reunir requisitos para migrar para o Power BI
description: Diretrizes sobre como reunir e priorizar requisitos ao migrar para o Power BI.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/20/2020
ms.author: v-pemyer
ms.openlocfilehash: 60a22946ccde642987e748904d0dc7fe636ec700
ms.sourcegitcommit: ffc46032d0771227395cc38be9ec9ff1500eac70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "89401969"
---
# <a name="gather-requirements-to-migrate-to-power-bi"></a>Reunir requisitos para migrar para o Power BI

Este artigo descreve o **Estágio 1**, que trata da reunião e priorização de requisitos ao migrar para o Power BI.

:::image type="content" source="media/powerbi-migration-requirements/migrate-to-powerbi-stage-1.png" alt-text="Imagem mostrando os estágios de uma migração para o Power BI. O Estágio 1 é enfatizado neste artigo.":::

> [!NOTE]
> Para obter uma explicação completa do gráfico acima, confira [Visão geral da migração para o Power BI](powerbi-migration-overview.md).

A ênfase do Estágio 1 está na coleta de informações e no planejamento de uma solução individual que será migrada para o Power BI.

A saída do Estágio 1 inclui os requisitos detalhados que foram priorizados. No entanto, será necessário concluir atividades adicionais nos Estágios 2 e 3 para estimar por completo o nível de esforços.

> [!IMPORTANT]
> Os Estágios de 1 a 5 representam atividades relacionadas a uma solução específica. Há decisões e atividades no nível organizacional/do locatário que afetam o processo no nível da solução. Algumas dessas atividades de planejamento de alto nível são discutidas no artigo [Visão geral da migração para o Power BI](powerbi-migration-overview.md). Quando apropriado, adie as decisões de nível organizacional quanto à eficiência e à consistência.

> [!TIP]
> A maioria dos tópicos discutidos neste artigo também se aplica a um projeto de implementação padrão do Power BI.

## <a name="compile-requirements"></a>Requisitos de compilação

O inventário de artefatos de BI existentes, compilado nas [etapas de pré-migração](powerbi-migration-pre-migration-steps.md), torna-se a entrada para os requisitos da nova solução a ser criada no Power BI. A coleta de requisitos é sobre a compreensão do estado atual, bem como os itens que os usuários gostariam de alterar ou refatorar quando os relatórios são reprojetados no Power BI. Os requisitos detalhados serão úteis para o planejamento de implantação da solução no [Estágio 2](powerbi-migration-planning.md), durante a criação de uma prova de conceito no [Estágio 3](powerbi-migration-proof-of-concept.md) e ao criar a solução pronta para produção no [Estágio 4](powerbi-migration-create-validate-content.md).

### <a name="gather-report-requirements"></a>Reunir requisitos de relatórios

Compile informações completas e fáceis de referenciar sobre os relatórios, como:

- **Finalidade, público-alvo e ação esperada:** identifique a finalidade e o processo de negócios aplicável a cada relatório, bem como o público-alvo, o fluxo de trabalho analítico e a ação esperada a ser executada pelos consumidores do relatório.
- **Como os consumidores usam o relatório:** considere a possibilidade de se sentar com os consumidores do relatório existente a fim de entender exatamente o que eles fazem com ele. Você pode aprender que determinados elementos do relatório podem ser eliminados ou melhorados na nova versão do Power BI. Esse processo envolve um investimento de tempo adicional, mas é valioso para relatórios críticos ou usados com frequência.
- **Proprietário e especialista no assunto:** identifique o proprietário do relatório e qualquer especialista no assunto associado ao relatório ou ao domínio de dados. Eles podem se tornar os proprietários do novo relatório do Power BI no futuro. Inclua quaisquer requisitos específicos de gerenciamento de alterações (que normalmente são diferentes entre as soluções gerenciadas pelo departamento de TI e pela área de negócios), bem como as aprovações, que serão necessárias quando as alterações forem feitas no futuro.
- **Método de entrega de conteúdo:** esclareça as expectativas do consumidor de relatório para a entrega de conteúdo. Pode ser sob demanda, execução interativa, incorporada em um aplicativo personalizado ou entrega em um agendamento usando uma assinatura de email. Também pode haver requisitos para disparar notificações de alerta.
- **Necessidades de interatividade:** determine os requisitos de interatividade _obrigatórios_ e _desejáveis_, como filtros ou análises detalhadas.
- **Fontes de dados:** verifique se todas as fontes de dados exigidas pelo relatório foram descobertas e se as necessidades de latência de dados (atualização de dados) foram compreendidas. Identifique os requisitos de dados históricos, tendência e instantâneo de dados para cada relatório de modo que eles possam estar alinhados aos requisitos de dados. A documentação da fonte de dados também pode ser útil posteriormente, ao executar a validação de dados de um novo relatório com os dados de origem.
- **Requisitos de segurança:** esclareça os requisitos de segurança (como visualizadores permitidos, editores permitidos e eventuais necessidades de segurança em nível de linha), incluindo as exceções à segurança organizacional normal. Documente qualquer nível de confidencialidade de dados, privacidade de dados ou necessidades normativas/de conformidade.
- **Cálculos, KPIs e regras de negócio:** identifique e documente todos os cálculos, KPIs e regras de negócio atualmente definidos no relatório existente para que eles possam ser alinhados com os requisitos de dados.
- **Requisitos de usabilidade, layout e cosméticos:** identifique necessidades específicas de usabilidade, layout e cosméticas relacionadas aos requisitos de visualização, agrupamento e classificação de dados e à visibilidade condicional. Inclua eventuais considerações específicas relacionadas à entrega de dispositivos móveis.
- **Necessidades de impressão e exportação:** determine se há requisitos específicos para impressão, exportação ou layout perfeito para pixels. Essas necessidades influenciarão o tipo de relatório que será mais adequado (como um Power BI, um Excel ou um relatório paginado). Lembre-se de que os consumidores de relatório tendem a dar muita importância à maneira como eles sempre fazem as coisas, portanto, não tenha medo de desafiar a forma de pensar deles. Ao se comunicar, não se esqueça fazer referência ao termo _melhorias_ em vez de _alterações_.
- **Riscos ou preocupações:** determine se há outros requisitos técnicos ou funcionais para os relatórios, bem como eventuais riscos ou preocupações sobre as informações apresentadas neles.
- **Problemas em aberto e itens da lista de pendências:** identifique qualquer manutenção futura, problemas conhecidos ou solicitações adiadas para adicionar à lista de pendências neste momento.

> [!TIP]
> Considere a classificação dos requisitos separando-os em _obrigatórios_ ou _desejáveis_. Frequentemente, os consumidores solicitam tudo aquilo de que podem precisar com antecedência, pois acreditam ser a única chance de fazer solicitações. Além disso, ao abordar as prioridades em várias iterações, torne a lista de pendências disponível para os stakeholders. Isso ajuda na comunicação, na tomada de decisões e no acompanhamento de compromissos pendentes.

### <a name="gather-data-requirements"></a>Reunir requisitos de dados

Compile informações detalhadas referentes aos dados, como:

- **Consultas existentes:** identifique se há consultas de relatório ou procedimentos armazenados existentes que podem ser usados por um [modelo DirectQuery](../connect-data/desktop-use-directquery.md) ou um [modelo composto](../transform-model/desktop-composite-models.md) ou que podem ser convertidos em um modelo de importação.
- **Tipos de fontes de dados:** compile os tipos de fontes de dados que são necessários, incluindo fontes de dados centralizadas (como uma data warehouse empresarial), bem como fontes de dados não padrão (como arquivos simples ou arquivos do Excel que aumentam as fontes de dados empresariais para fins de relatório). Encontrar o local em que as fontes de dados estão localizadas, para fins de conectividade do [gateway de dados](../connect-data/service-gateway-onprem.md), também é importante.
- **Necessidades de estrutura de dados e limpeza:** determine a estrutura de dados para cada fonte de dados de requisito e até que ponto as atividades de [limpeza de dados](../transform-model/desktop-query-overview.md) são necessárias.
- **Integração de dados:** avalie como a integração de dados será tratada quando houver várias fontes de dados e como as [relações](../transform-model/desktop-create-and-manage-relationships.md) podem ser definidas entre cada tabela de modelo. Identifique os elementos de dados específicos necessários para simplificar o modelo e [reduzir o tamanho](import-modeling-data-reduction.md).
- **Latência de dados aceitável:** determine as necessidades de latência de dados para cada fonte de dados. Isso influenciará as decisões sobre qual [modo de armazenamento de dados](../transform-model/desktop-storage-mode.md) usar. Também é importante conhecer a frequência de atualização de dados das tabelas de modelo de importação.
- **Escalabilidade e volume de dados:** avalie as expectativas de volume de dados, que serão fatoradas em decisões sobre [suporte a modelos grandes](../admin/service-premium-large-models.md) e o design do [modelos compostos](../transform-model/desktop-composite-models.md) ou do DirectQuery. Também é essencial conhecer as considerações relacionadas às necessidades de dados históricos. Para conjuntos de dados maiores, também será necessário determinar as regras de [atualização de dados incrementais](../admin/service-premium-incremental-refresh.md).
- **Medidas, KPIs e regras de negócios:** avaliar as necessidades de medidas, KPIs e regras de negócios. Eles afetarão as decisões referentes a onde aplicar a lógica: no conjunto de dados ou no processo de integração de dados.
- **Dados mestres e catálogo de dados:** considere se há problemas de dados mestres que exigem atenção. Determine se a integração com um catálogo de dados corporativo é apropriada para melhorar a descoberta, acessar definições ou produzir uma terminologia consistente aceita pela organização.
- **Segurança e privacidade de dados:** determine se há alguma consideração de privacidade de dados ou segurança específica para conjuntos de dados, incluindo os requisitos de [segurança em nível de linha](../admin/service-admin-rls.md).
- **Problemas em aberto e itens da lista de pendências:** adicione todos os problemas conhecidos, defeitos de qualidade de dados conhecidos, manutenções futuras ou solicitações adiadas à lista de pendências neste momento.

> [!IMPORTANT]
> A reutilização de dados pode ser alcançada com os [conjuntos de dados compartilhados](../connect-data/service-datasets-share.md), que, opcionalmente, pode ser [certificados](../connect-data/service-datasets-certify.md) para indicar a confiabilidade e melhorar a capacidade de descoberta. A reutilização da preparação de dados pode ser alcançada com [fluxos de dados](../transform-model/service-dataflows-overview.md) a fim de reduzir a lógica repetitiva em vários conjuntos de dados. Os fluxos de dados também podem reduzir significativamente a carga em sistemas de origem, pois os dados são recuperados com menos frequência – então, vários conjuntos de dados podem importar dados do fluxo de dados.

## <a name="identify-improvement-opportunities"></a>Identificar oportunidades de melhoria

Na maioria das situações, ocorrem algumas modificações e melhorias. É raro que uma migração direta de um para um ocorra sem qualquer refatoração ou melhoria. Três tipos de melhorias que você pode considerar são:

- **Consolidação de relatórios:** relatórios semelhantes podem ser consolidados usando técnicas como filtros, marcadores ou personalização. Ter menos relatórios, mais flexíveis, pode melhorar significativamente a experiência dos consumidores de relatórios. Considere a otimização de conjuntos de dados para [P e R (consulta de linguagem natural)](../natural-language/q-and-a-best-practices.md) a fim de oferecer uma flexibilidade ainda maior para os consumidores de relatórios, permitindo que eles criem suas próprias visualizações.
- **Melhorias de eficiência:** durante a coleta de requisitos, muitas vezes é possível identificar melhorias. Por exemplo, quando os analistas compilam números manualmente ou quando um fluxo de trabalho pode ser simplificado. O [Power Query](../transform-model/desktop-query-overview.md) pode desempenhar uma grande função na substituição de atividades manuais que estão atualmente em execução. Se os analistas de negócios se encontrarem executando as mesmas atividades para limpar e preparar dados regularmente, as etapas repetíveis de preparação de dados do Power Query poderão gerar uma economia de tempo significativa e reduzir o número de erros.
- **Centralização do modelo de dados:** um conjunto de dados autoritário e certificado serve como o backbone do autoatendimento de BI gerenciado. Nesse caso, os dados são gerenciados uma vez e os analistas têm a flexibilidade de usar e aumentar esses dados para atender às suas necessidades de relatório e análise.

> [!NOTE]
> Para obter mais informações sobre a centralização de modelos de dados, leia sobre a [disciplina no núcleo](center-of-excellence-microsoft-business-intelligence-transformation.md#discipline-at-the-core) e a [flexibilidade na borda](center-of-excellence-microsoft-business-intelligence-transformation.md#flexibility-at-the-edge).

## <a name="prioritize-and-assess-complexity"></a>Priorizar e avaliar a complexidade

Neste ponto, o inventário inicial está disponível e pode incluir requisitos específicos. Ao priorizar o conjunto inicial de artefatos de BI prontos para migração, os relatórios e os dados devem ser considerados coletivamente e independentemente um do outro.

Identifique relatórios de alta prioridade, que podem incluir relatórios que:

- Trazem valor significativo para os negócios.
- São executadas com frequência.
- São exigidos pela alta liderança ou pelos executivos seniores.
- Envolvam um nível razoável de complexidade (para melhorar as chances de sucesso durante as iterações de migração iniciais).

Identifique dados de alta prioridade, que podem incluir dados que:

- Contém elementos de dados críticos.
- São dados organizacionais comuns que se aplicam a muitos casos de uso.
- Podem ser usados para criar um conjunto de dados compartilhado para reutilização em relatórios e por muitos criadores de relatório.
- Envolvam um nível razoável de complexidade (para melhorar as chances de sucesso nas iterações de migração iniciais).

## <a name="next-steps"></a>Próximas etapas

No [próximo artigo desta série sobre migração do Power BI](powerbi-migration-planning.md), saiba mais sobre o Estágio 2, que trata do planejamento da migração de uma solução do Power BI.

Outros recursos úteis incluem:

- [Transformação de BI da Microsoft](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [White paper de Planejamento de uma implantação empresarial do Power BI](https://aka.ms/PBIEnterpriseDeploymentWP)
- Dúvidas? [Experimente perguntar à Comunidade do Power BI](https://community.powerbi.com/)
- Sugestões? [Contribuir com ideias para aprimorar o Power BI](https://ideas.powerbi.com/)

Parceiros experientes do Power BI estão disponíveis para ajudar sua organização a alcançar sucesso no processo de migração. Para envolver um parceiro do Power BI, visite o [portal de parceiro de Power BI](https://powerbi.microsoft.com/partners/).
