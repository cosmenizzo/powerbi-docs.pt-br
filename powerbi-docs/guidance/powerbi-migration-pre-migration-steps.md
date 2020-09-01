---
title: Preparar para migrar para o Power BI
description: Diretrizes sobre as etapas de pré-migração ao migrar para o Power BI.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/20/2020
ms.author: v-pemyer
ms.openlocfilehash: 9a5ed3d2a4798332de2394e1ad5be6fdbdb6eeae
ms.sourcegitcommit: 84e75a2cd92f4ba4e0c08ba296b981b79d6d0e82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88803104"
---
# <a name="prepare-to-migrate-to-power-bi"></a>Preparar para migrar para o Power BI

Este artigo descreve as ações que você pode considerar antes de migrar para o Power BI.

:::image type="content" source="media/powerbi-migration-pre-migration-steps/migrate-to-powerbi-pre-migration-steps.png" alt-text="Imagem mostrando os estágios de uma migração para o Power BI. As etapas pré-migração são enfatizadas para este artigo.":::

> [!NOTE]
> Para obter uma explicação completa do gráfico acima, confira [Visão geral da migração para o Power BI](powerbi-migration-overview.md).

As etapas pré-migração enfatizam o planejamento antecipado, que é uma preparação importante antes de passar pelos cinco estágios de migração. A maioria das etapas de pré-migração ocorrerá uma vez, embora, para organizações maiores, algumas partes possam ser iterativas para cada unidade de negócios ou área departamental.

A saída das etapas de pré-migração inclui um modelo de governança inicial, o planejamento inicial de implantação de alto nível, além de um inventário dos relatórios e dos dados a serem migrados. Informações adicionais de atividades nos estágios 1, 2 e 3 serão necessárias para estimar totalmente o nível de esforço para a migração de soluções individuais.

> [!TIP]
> A maioria dos tópicos discutidos neste artigo também se aplica a um projeto de implementação padrão do Power BI.

## <a name="create-costbenefit-analysis-and-evaluation"></a>Criar análise de custo/benefício e avaliação

Várias considerações principais durante a avaliação inicial incluem obter:

- Clareza no caso de negócios e na estratégia de BI para alcançar um estado futuro desejado específico.
- Clareza do que significa sucesso e como medir o progresso e o sucesso da iniciativa de migração.
- Estimativas de custo e resultados de cálculo de ROI (retorno sobre o investimento).
- Resultados bem-sucedidos para várias iniciativas produtivas do Power BI com escopo e complexidade menores.

## <a name="identify-stakeholders-and-executive-support"></a>Identificar participantes e suporte executivo

As várias considerações para identificar os participantes incluem:

- Garantir o alinhamento com as partes interessadas no caso comercial e na estratégia de BI.
- Incluir representantes de todas as unidades de negócios, mesmo que o conteúdo esteja programado para migração posterior, para entender suas motivações e preocupações.
- Envolver os líderes de Power BI antecipadamente.
- Criar e seguir um plano de comunicação com participantes.

> [!TIP]
> Se você teme que está começando a se comunicar em excesso, é provável que tenha razão.

## <a name="generate-initial-governance-model"></a>Gerar modelo de governança inicial

Vários itens importantes a serem abordados no início de uma implementação do Power BI incluem:

- Metas específicas para a adoção do Power BI e como o Power BI encaixa na estratégia geral de BI para a organização.
- Como a função de administrador do Power BI será tratada, especialmente em organizações descentralizadas.
- Políticas relacionadas à obtenção de dados confiáveis: uso de fontes de dados autoritativas, tratamento de problemas de qualidade de dados e uso de terminologia consistente e definições comuns.
- Estratégia de privacidade de dados e segurança para fontes de dados, modelos de dados, relatórios e distribuição de conteúdo para usuários internos e externos.
- Como os requisitos de conformidade interna e externa, regulamentação e auditoria serão atendidos.

> [!IMPORTANT]
> O modelo de governança mais eficaz busca equilibrar a capacitação do usuário com o nível de controle necessário. Veja mais informações, leia sobre a [disciplina no núcleo](center-of-excellence-microsoft-business-intelligence-transformation.md#discipline-at-the-core) e a [flexibilidade na borda](center-of-excellence-microsoft-business-intelligence-transformation.md#flexibility-at-the-edge).

## <a name="conduct-initial-deployment-planning"></a>Conduzir planejamento de implantação inicial

O planejamento de implantação inicial envolve a definição de padrões, políticas e preferências para a implementação do Power BI da organização.

Observe que o [Estágio 2](powerbi-migration-planning.md) faz referência ao planejamento de implantação no nível da solução. As atividades do Estágio 2 devem respeitar as decisões de nível organizacional sempre que possível.

Alguns itens críticos a serem abordados no início de uma implementação do Power BI incluem:

- Decisões de [configuração do administrador de locatário do Power BI](admin-tenant-settings.md), que devem ser documentadas.
- Decisões de [gerenciamento do workspace](../collaborate-share/service-new-workspaces.md), que devem ser documentadas.
- Considerações e preferências relacionadas a dados e [métodos de distribuição de conteúdo](../collaborate-share/service-how-to-collaborate-distribute-dashboards-reports.md), como aplicativos, workspaces compartilhamento, assinaturas e inserção de conteúdo.
- As preferências relacionadas aos [modos de conjunto de dados](../connect-data/service-dataset-modes-understand.md), como o uso do modo de importação, o modo DirectQuery ou a combinação dos dois modos em um [modelo composto](composite-model-guidance.md).
- [Proteção de dados e acesso](../admin/service-admin-power-bi-security.md).
- Trabalhando com [conjuntos de dados compartilhados](../connect-data/service-datasets-share.md) para reutilização.
- Aplicar [certificação de dados](../connect-data/service-datasets-certify.md) para promover o uso de dados autoritativos e confiáveis.
- Uso de diferentes [tipos de relatório](../create-reports/index.yml), incluindo relatórios do Power BI, relatórios do Excel ou relatórios paginados para diferentes casos de uso ou unidades de negócios.
- Abordagens de gerenciamento de alterações para gerenciar artefatos de BI centralizados e artefatos de BI gerenciados por negócios.
- Planos de treinamento para consumidores, modeladores de dados, autores de relatórios e administradores.
- Suporte para autores de conteúdo usando [modelos do Power BI Desktop](../create-reports/desktop-templates.md), [visuais personalizados](https://powerbi.microsoft.com/blog/how-to-govern-power-bi-visuals-inside-your-organization/) e padrões de design de relatório documentados.
- Procedimentos e processos para gerenciar requisitos de usuário, como solicitação de novas licenças, adição de fontes de dados de gateway, obtenção de permissão para fontes de dados de gateway, solicitação de novos workspaces, alterações de permissões de workspace e outros requisitos comuns que podem ser encontrados regularmente.

> [!IMPORTANT]
> O planejamento da implantação é um processo iterativo. As decisões de implantação serão refinadas e aumentadas muitas vezes à medida que a experiência da sua organização com o Power BI aumenta e conforme o Power BI evolui. As decisões tomadas durante esse processo serão usadas durante o planejamento da implantação no nível da solução discutido no [Estágio 2](powerbi-migration-planning.md) do processo de migração.

## <a name="establish-initial-architecture"></a>Estabelecer a arquitetura inicial

Sua [arquitetura da solução de BI](center-of-excellence-business-intelligence-solution-architecture.md) vai evoluir e amadurecer ao longo do tempo. As tarefas de instalação do Power BI a tratar imediatamente incluem:

- Instalação do locatário do Power BI e integração com o Azure Active Directory.
- Definir os [administradores do Power BI](../admin/service-admin-role.md).
- Adquirir e atribuir [licenças de usuário](../admin/service-admin-licensing-organization.md) iniciais.
- Configurar e examinar [configurações de administração de locatários do Power BI](admin-tenant-settings.md).
- Configurar [funções de workspace](../collaborate-share/service-new-workspaces.md#roles-in-the-new-workspaces) e atribuir acesso a grupos de segurança e usuários do Azure Active Directory.
- Configurar um cluster de [gateway de dados](../connect-data/service-gateway-deployment-guidance.md) inicial, com um plano para atualizar regularmente.
- Adquirir [licença de capacidade Premium](../admin/service-admin-premium-purchase.md) inicial (se aplicável).
- Configurar as [cargas de trabalho de capacidade Premium](../admin/service-admin-premium-workloads.md) – com um plano para gerenciar de maneira contínua.

## <a name="define-success-criteria-for-migration"></a>Definir critérios de êxito para migração

A primeira tarefa é entender o que é o sucesso na migração de uma solução individual. As perguntas que você pode fazer incluem:

- **Quais são as motivações e os objetivos específicos dessa migração?** Para obter mais informações, confira [Visão geral da migração do Power BI (considere as razões para a migração)](powerbi-migration-overview.md#consider-migration-reasons). Este artigo descreve os motivos mais comuns para migrar para o Power BI. Certamente, seus objetivos devem ser especificados no nível organizacional. Além disso, a migração de uma solução de BI herdada pode se beneficiar muito da economia de custos, enquanto migrar uma solução de BI herdada diferente pode se concentrar em obter os benefícios da otimização do fluxo de trabalho.
- **Qual é o custo/benefício ou ROI esperado para essa migração?** Ter uma compreensão clara das expectativas relacionadas a custo, aumentos de capacidade, reduções de complexidade ou mais agilidade é útil para medir o sucesso. Pode fornecer princípios de orientação para ajudar na tomada de decisões durante o processo de migração.
- **Quais KPIs (indicadores chave de desempenho) serão usados para medir o sucesso?** A lista a seguir apresenta alguns exemplos de KPIs:
    - Número de relatórios renderizados da plataforma de BI herdada, diminuindo o mês ao mês.
    - Número de relatórios renderizados do Power BI, aumentando mês ao a mês.
    - Número de consumidores de relatório do Power BI, aumentando trimestre a trimestre.
    - Percentual de relatórios migrados para produção por data de destino.
    - Redução de custos de licenciamento ano a ano.

> [!TIP]
> O [log de atividades do Power BI](../admin/service-admin-auditing.md) pode ser usado como uma fonte para medir o andamento do KPI.

## <a name="prepare-inventory-of-existing-reports"></a>Preparar o inventário de relatórios existentes

Preparar um inventário de relatórios existentes na plataforma de BI herdada é uma etapa crítica para entender o que já existe. O resultado desta etapa é uma entrada para avaliar o nível do esforço de migração. As atividades relacionadas à preparação de um inventário podem incluir:

1. **Inventário de relatórios:** compile uma lista de relatórios e dashboards candidatos à migração.
2. **Inventário de fontes de dados:** compile uma lista de todas as fontes de dados acessadas por relatórios existentes. Deve incluir fontes de dados empresariais, bem como fontes de dados departamentais e pessoais. Esse processo pode revelar fontes de dados que anteriormente não eram conhecidas pelo departamento de TI, muitas vezes chamadas de _TI de sombra_.
3. **Log de auditoria:** obtenha dados do log de auditoria da plataforma de BI herdada para entender os padrões de uso e auxiliar na priorização. As informações importantes a serem obtidas do log de auditoria incluem:
    - Número médio de vezes que cada relatório foi executado por semana/mês/trimestre.
    - Número médio de consumidores por relatório por semana/mês/trimestre.
    - Os consumidores de cada relatório, particularmente os relatórios usados por executivos.
    - A data mais recente em que cada relatório foi executado.

> [!NOTE]
> Em muitos casos, o conteúdo não é migrado para o Power BI exatamente como está. A migração representa uma oportunidade de reprojetar a arquitetura de dados e/ou melhorar a entrega de relatórios. A compilação de um inventário de relatórios é crucial para entender o que existe atualmente para que você possa começar a avaliar qual refatoração precisa ocorrer. Os artigos restantes desta série descrevem possíveis aprimoramentos mais detalhadamente.

## <a name="explore-automation-options"></a>Explorar opções de automação

Não é possível automatizar completamente um processo de conversão do Power BI de ponta a ponta.

A compilação do inventário existente de dados e relatórios é um possível candidato à automação quando você tem uma ferramenta existente que pode fazer isso para você. A extensão para a qual a automação pode ser usada para algumas partes do processo de migração, como a compilação do inventário existente, depende muito das ferramentas que você tem.

## <a name="next-steps"></a>Próximas etapas

No [próximo artigo desta série de migração do Power BI](powerbi-migration-requirements.md), saiba mais sobre o Estágio 1, que trata da coleta e da priorização de requisitos ao migrar para o Power BI.

Outros recursos úteis incluem:

- [Transformação de BI da Microsoft](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [White paper de Planejamento de uma implantação empresarial do Power BI](https://aka.ms/PBIEnterpriseDeploymentWP)
- Dúvidas? [Experimente perguntar à Comunidade do Power BI](https://community.powerbi.com/)
- Sugestões? [Contribuir com ideias para aprimorar o Power BI](https://ideas.powerbi.com/)

Parceiros experientes do Power BI estão disponíveis para ajudar sua organização a alcançar sucesso no processo de migração. Para envolver um parceiro do Power BI, visite o [portal de parceiro de Power BI](https://powerbi.microsoft.com/partners/).
