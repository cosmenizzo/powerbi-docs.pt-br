---
title: Visão geral da migração para o Power BI
description: Saiba como planejar e realizar uma migração de outra ferramenta de BI de terceiros para o Power BI.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/20/2020
ms.author: v-pemyer
ms.openlocfilehash: aa17e6293a4bd946b1d6b7acad45623fa2393c57
ms.sourcegitcommit: 84e75a2cd92f4ba4e0c08ba296b981b79d6d0e82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88803123"
---
# <a name="power-bi-migration-overview"></a>Visão geral da migração para o Power BI

Os clientes estão cada vez mais padronizando o Power BI como a ferramenta para impulsionar uma cultura de dados que envolva a habilitação do SSBI (business intelligence de autoatendimento) gerenciado, a racionalização da entrega do BI empresarial e a abordagem das pressões econômicas. A finalidade desta série de artigos sobre migração para o Power BI é fornecer diretrizes sobre como planejar e realizar a migração de uma ferramenta de BI de terceiros para o Power BI.

Os artigos na série de migração para o Power BI incluem:

1. Visão geral de migração para o Power BI (este artigo)
1. [Preparar para migrar para o Power BI](powerbi-migration-pre-migration-steps.md)
1. [Reunir requisitos para migrar para o Power BI (Estágio 1)](powerbi-migration-requirements.md)
1. [Planejar a implantação para migrar para o Power BI (Estágio 2)](powerbi-migration-planning.md)
1. [Realizar prova de conceito para migrar para o Power BI (Estágio 3)](powerbi-migration-proof-of-concept.md)
1. [Criar conteúdo para migrar para o Power BI (Estágio 4)](powerbi-migration-create-validate-content.md)
1. [Implantar no Power BI (Estágio 5)](powerbi-migration-deploy-support-monitor.md)
1. [Aprender com as migrações dos clientes para o Power BI](powerbi-migration-learn-from-customers.md)

Há duas suposições: Sua organização tem implantada atualmente uma plataforma de BI herdada e já tomou a decisão de migrar formalmente o conteúdo e os usuários para o Power BI. Migrar para a serviço do Power BI é o foco principal desta série. Pode haver considerações adicionais aplicáveis a clientes de nuvem nacionais além do que é discutido nesta série de artigos.

O diagrama a seguir mostra quatro fases de alto nível para a implantação do Power BI na sua organização.

:::image type="content" source="media/powerbi-migration-overview/migrate-to-powerbi-high-level-overview.png" alt-text="Imagem mostrando as quatro fases de alto nível que são descritas na tabela a seguir.":::

|Fase|Descrição|
|--------|-----------|
|![Fase 1.](media/common/icon-01-red-30x30.png)|**Configurar e avaliar o Power BI.** A primeira fase envolve o estabelecimento da arquitetura inicial do Power BI. A implantação preliminar e o planejamento de governança são tratados neste ponto, bem como as avaliações do Power BI, incluindo as análises de retorno sobre o investimento e/ou de custo benefício.|
|![Fase 2.](media/common/icon-02-red-30x30.png)|**Criar soluções rapidamente no Power BI.** Na segunda fase, os criadores de BI de autoatendimento podem começar a usar e avaliar o Power BI para as necessidades deles, obtendo valor do Power BI rapidamente. As atividades da fase 2 atribuem importância à agilidade e à rapidez para obter valor de negócio, que é essencial para conquistar aceitação ao selecionar uma nova ferramenta de BI, como o Power BI. Por esse motivo, o diagrama retrata as atividades da fase 2 ocorrendo lado a lado com as atividades de migração da fase 3.|
|![Fase 3.](media/common/icon-03-red-30x30.png)|**Migrar ativos de BI da plataforma herdada para o Power BI.** A terceira fase aborda a migração para o Power BI. Esse é o foco desta série de artigos sobre migração para o Power BI. Cinco estágios de migração específicos são discutidos na próxima seção.|
|![Fase 4.](media/common/icon-04-red-30x30.png)|**Adotar, administrar e monitorar o Power BI.** A fase final consiste em atividades contínuas, como a criação de uma cultura de dados, comunicação e treinamento. Essas atividades impactam significativamente na implementação efetiva do Power BI. É importante ter políticas e processos de governança e segurança que sejam apropriados para a sua organização, bem como um esquema de auditoria e monitoramento que lhe permita dimensionar, crescer e melhorar continuamente.|

> [!IMPORTANT]
> Uma migração formal para o Power BI quase sempre ocorre em paralelo com o desenvolvimento de uma nova solução do Power BI. _Solução do Power BI_ é um termo genérico que abrange o uso de dados e de relatórios. Um arquivo pbix (Power BI Desktop) pode conter um modelo de dados, um relatório ou ambos. [A separação do modelo de dados dos relatórios](../guidance/report-separate-from-model.md) é incentivada para fins de reutilização de dados, mas não é obrigatória.
>
> O uso do Power BI para criar novos requisitos enquanto você planeja e realiza a migração formal ajudará a conquistar adesão. Fases simultâneas fornecem aos criadores de conteúdo uma experiência prática e real com o Power BI.

## <a name="five-stages-of-a-power-bi-migration"></a>Cinco estágios de uma migração do Power BI

A fase 3 do diagrama aborda a migração para o Power BI. Durante essa fase, há cinco estágios comuns.

:::image type="content" source="media/powerbi-migration-overview/migrate-to-powerbi-five-stages.png" alt-text="Imagem mostrando os estágios de uma migração para o Power BI, que são descritos a seguir.":::

Os seguintes estágios mostrados no diagrama anterior são:

- [Etapas de pré-migração](#pre-migration-steps)
- [Estágio 1: reunir requisitos e priorizar](#stage-1-gather-requirements-and-prioritize)
- [Estágio 2: planejar a implantação](#stage-2-plan-for-deployment)
- [Estágio 3: realizar prova de conceito](#stage-3-conduct-proof-of-concept)
- [Estágio 4: criar e validar conteúdo](#stage-4-create-and-validate-content)
- [Estágio 5: implantar, dar suporte e monitorar](#stage-5-deploy-support-and-monitor)

### <a name="pre-migration-steps"></a>Etapas de pré-migração

As etapas de pré-migração incluem ações que você pode considerar antes de iniciar um projeto a fim de migrar o conteúdo de uma plataforma de BI herdada para o Power BI. Elas normalmente incluem o planejamento inicial de implantação no nível do locatário. Para obter mais informações sobre essas atividades, confira [Preparar para migrar para o Power BI](powerbi-migration-pre-migration-steps.md).

### <a name="stage-1-gather-requirements-and-prioritize"></a>Etapa 1: reunir requisitos e priorizar

A ênfase do Estágio 1 está na coleta de informações e no planejamento da migração de uma solução. Esse processo deve ser iterativo e ter como escopo um esforço de tamanho razoável. A saída do Estágio 1 inclui um estoque priorizado de relatórios e dados que devem ser migrados. São necessárias atividades adicionais nos Estágios 2 e 3 para estimar por completo o nível de esforço. Para obter mais informações sobre as atividades do Estágio 1, confira [Reunir requisitos para migrar para o Power BI](powerbi-migration-requirements.md).

### <a name="stage-2-plan-for-deployment"></a>Etapa 2: planejar a implantação

O foco do Estágio 2 está em como os requisitos definidos no Estágio 1 podem ser atendidos para cada solução específica. A saída do Estágio 2 inclui o máximo de especificações possível para orientar o processo, embora seja um processo interativo e não linear. A criação de uma prova de conceito (no Estágio 3) pode ocorrer em paralelo com esse estágio. Mesmo durante a criação da solução (no Estágio 4), informações adicionais que influenciam as decisões de planejamento da implantação podem ser descobertas. Esse tipo de planejamento da implantação no Estágio 2 se concentra no nível da solução, ao mesmo tempo em que respeita as decisões já tomadas no nível organizacional. Para obter mais informações sobre as atividades do Estágio 2, confira [Planejar a implantação para migrar para o Power BI](powerbi-migration-planning.md).

### <a name="stage-3-conduct-proof-of-concept"></a>Etapa 3: realizar prova de conceito

A ênfase do Estágio 3 é abordar elementos desconhecidos e mitigar riscos o mais cedo possível. Uma POC (prova de conceito) técnica é útil para validar suposições e pode ser feita de maneira iterativa, juntamente com o planejamento da implantação (Estágio 2). A saída desse estágio é uma solução do Power BI com escopo restrito. Observe que não pretendemos que a POC seja um trabalho descartável. No entanto, provavelmente será necessário um trabalho adicional no Estágio 4 para deixá-la pronta para a produção. Nesse sentido, dentro da sua organização você pode se referir a essa atividade como um protótipo, um piloto, uma maquete, um início rápido ou um MVP (produto minimamente viável). A realização de uma POC nem sempre é necessária e pode ser feita informalmente. Para obter mais informações sobre as atividades do Estágio 3, confira [Realizar prova de conceito para migrar para o Power BI](powerbi-migration-proof-of-concept.md).

### <a name="stage-4-create-and-validate-content"></a>Estágio 4: criar e validar conteúdo

O Estágio 4 é quando ocorre, de fato, o trabalho de converter a POC em uma solução pronta para a produção. A saída desse estágio é uma solução concluída do Power BI que foi validada em um ambiente de desenvolvimento. Ela deve estar pronta para implantação no Estágio 5. Para obter mais informações sobre as atividades do Estágio 4, confira [Criar conteúdo para migrar para o Power BI](powerbi-migration-create-validate-content.md).

### <a name="stage-5-deploy-support-and-monitor"></a>Estágio 5: implantar, dar suporte e monitorar

O foco principal do Estágio 5 é implantar a nova solução do Power BI em produção. A saída desse estágio é uma solução de produção usada ativamente por usuários de negócios. Ao usar uma metodologia ágil, é aceitável ter algumas melhorias planejadas que serão entregues em uma iteração futura. Dependendo do seu nível de experiência com o Power BI (como na minimização de riscos ou na interrupção de usuários), você poderá optar por fazer uma implantação em estágios. Ou, inicialmente, você poderá implantar para um grupo menor de usuários piloto. O suporte e o monitoramento também são importantes nesse estágio e continuamente. Para obter mais informações sobre as atividades do Estágio 5, confira [Migrar para o Power BI](powerbi-migration-deploy-support-monitor.md).

> [!TIP]
> A maioria dos conceitos discutidos em toda esta série de artigos sobre migração para o Power BI também se aplica a um projeto de implementação padrão do Power BI.

## <a name="consider-migration-reasons"></a>Considere os motivos da migração

A habilitação de uma cultura de dados produtiva e íntegra é uma das principais metas de muitas organizações. O Power BI é uma excelente ferramenta para facilitar esse objetivo. Três motivos comuns que você pode considerar ao migrar para o Power BI podem ser resumidos em:

- **Habilitar o BI de autoatendimento gerenciado** introduzindo novos recursos que capacitam a comunidade de usuários do BI de autoatendimento. O Power BI torna o acesso às informações e à tomada de decisões mais amplamente disponível, ao mesmo tempo em que depende menos de habilidades especializadas que podem ser difíceis de encontrar.
- **Racionalizar a entrega do BI empresarial** para atender aos requisitos que não são abordados pelas ferramentas de BI existentes, ao mesmo tempo diminuindo o nível de complexidade, reduzindo o custo de propriedade e/ou padronizando as diversas ferramentas de BI atualmente em uso.
- **Abordar pressões econômicas** para aumentar a produtividade com menos recursos, tempo e pessoal.

## <a name="achieve-power-bi-migration-success"></a>Alcançar sucesso na migração para o Power BI

Cada migração é ligeiramente diferente. Ela pode depender da estrutura organizacional, das estratégias de dados, da maturidade do gerenciamento de dados e dos objetivos organizacionais. No entanto, há algumas práticas que vemos com frequência nos clientes que alcançam sucesso na migração do Power BI.

- **Patrocínio executivo:** identifique o patrocinador executivo no início do processo. Essa pessoa deve ser alguém que fornece ativamente suporte ao BI na organização e que se dedica pessoalmente a alcançar um resultado positivo na migração. O ideal é que o patrocinador executivo tenha total autoridade e responsabilidade sobre os resultados relacionados ao Power BI.
- **Treinamento, suporte e comunicação:** reconheça que é mais do que apenas uma iniciativa de tecnologia. Qualquer projeto de BI ou de análise também é uma iniciativa de pessoas, portanto, considere a possibilidade de investir em treinamento e suporte ao usuário logo no início. Além disso, crie um plano de comunicação que explique de modo transparente para todos os stakeholders o que e por que está ocorrendo e que defina expectativas realistas. Verifique se você incluiu um loop de comentários em seu plano de comunicação para capturar a entrada dos stakeholders.
- **Vitórias rápidas:** inicialmente, priorize os itens de alto valor que têm valor de negócios tangível e que são urgentes. Em vez de sempre tentar migrar os relatórios com precisão à medida que aparecem na plataforma de BI herdada, concentre-se na pergunta de negócios que o relatório está tentando responder (incluindo a ação a ser executada) ao abordar o relatório reprojetado.
- **Modernização e melhorias:** esteja disposto a repensar a maneira como as coisas sempre foram feitas. Uma migração pode fornecer oportunidades de entregar melhorias. Por exemplo, ela pode eliminar a preparação de dados manual ou realocar as regras de negócio que foram confinadas em um único relatório. Considere a possibilidade de refatorar, modernizar e consolidar as soluções existentes quando o esforço puder ser justificado. Isso pode incluir a consolidação de vários relatórios em um ou a eliminação de artefatos herdados que não são usados há algum tempo.
- **Aprendizado contínuo:** esteja preparado para usar uma abordagem em fases, ao mesmo tempo aprendendo e se adaptando continuamente. Trabalhe em ciclos iterativos curtos para agregar valor rapidamente. Torne uma prática frequente concluir pequenas POCs para minimizar o risco de elementos desconhecidos, validar suposições e aprender sobre novos recursos. Como o Power BI é um serviço de nuvem atualizado mensalmente, é importante se manter por dentro dos desenvolvimentos e ajustar o curso quando necessário.
- **Resistência a alterações:** entenda que pode haver níveis variados de resistência a alterações; alguns usuários resistem ao aprendizado de uma nova ferramenta. Além disso, alguns profissionais que dedicaram tempo e esforços significativos para aprender uma ferramenta de BI diferente podem temer serem substituídos. Esteja preparado, pois isso pode resultar em dificuldades políticas internas, especialmente em organizações altamente descentralizadas.
- **Restrições:** seja realista com os planos de migração, incluindo financiamento, estimativas de tempo, funções e responsabilidades de todos os envolvidos.

## <a name="acknowledgments"></a>Agradecimentos

Esta série de artigos foi escrita por Melissa Coates, MVP de Plataforma de Dados e proprietária das [Estratégias de Dados de Coates](https://www.coatesdatastrategies.com/). Dentre os colaboradores e revisores estão Marc Reguera, Venkatesh Titte, Patrick Baumgartner, Tamer Farag, Richard Tkachuk, Matthew Roche, Adam Saxton, Chris Webb, Mark Vaillancourt, Daniel Rubiolo, David Iseminger e Peter Myers.

## <a name="next-steps"></a>Próximas etapas

No [próximo artigo desta série de migração para o Power BI](powerbi-migration-pre-migration-steps.md), saiba mais sobre as etapas de pré-migração ao migrar para o Power BI.

Outros recursos úteis incluem:

- [Transformação de BI da Microsoft](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [White paper de Planejamento de uma implantação empresarial do Power BI](https://aka.ms/PBIEnterpriseDeploymentWP)
- [Migrar relatórios SSRS para o Power BI](migrate-ssrs-reports-to-power-bi.md)
- Dúvidas? [Experimente perguntar à Comunidade do Power BI](https://community.powerbi.com/)
- Sugestões? [Contribuir com ideias para aprimorar o Power BI](https://ideas.powerbi.com/)

Parceiros experientes do Power BI estão disponíveis para ajudar sua organização a alcançar sucesso no processo de migração. Para envolver um parceiro do Power BI, visite o [portal de parceiro de Power BI](https://powerbi.microsoft.com/partners/).
