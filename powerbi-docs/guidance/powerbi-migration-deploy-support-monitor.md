---
title: Implantar no Power BI
description: Diretrizes sobre implantação, o suporte e o monitoramento de conteúdo ao migrar para o Power BI.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/20/2020
ms.author: v-pemyer
ms.openlocfilehash: 23d207bb4f070c3c3a35f1e74dd281f012528c82
ms.sourcegitcommit: cff93e604e2c5f24e0f03d6dbdcd10c2332aa487
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90964996"
---
# <a name="deploy-to-power-bi"></a>Implantar no Power BI

Este artigo descreve o **Estágio 5**, que trata da implantação, do suporte e do monitoramento de conteúdo ao migrar para o Power BI.

:::image type="content" source="media/powerbi-migration-deploy-support-monitor/migrate-to-powerbi-stage-5.png" alt-text="Imagem mostrando os estágios de uma migração para o Power BI. O Estágio 5 é enfatizado neste artigo.":::

> [!NOTE]
> Para obter uma explicação completa do gráfico acima, confira [Visão geral da migração para o Power BI](powerbi-migration-overview.md).

O foco principal do Estágio 5 é implantar a nova solução do Power BI em produção.

A saída deste estágio é uma solução de produção pronta para ser usada pela empresa. Ao se trabalhar com um método ágil, é aceitável ter algumas melhorias planejadas que serão entregues em uma iteração futura. O suporte e o monitoramento também são importantes nesse estágio e continuamente.

> [!TIP]
> Exceto quanto à execução em paralelo e à desativação dos relatórios herdados, que são discutidos abaixo, os tópicos discutidos neste artigo também se aplicam a um projeto de implementação padrão do Power BI.

## <a name="deploy-to-test-environment"></a>Implantar no ambiente de teste

Para soluções gerenciadas por TI ou soluções que são essenciais para a produtividade dos negócios, geralmente há um ambiente de teste. O ambiente de teste fica entre os ambientes de desenvolvimento e de produção e ele não é necessário para todas as soluções do Power BI. O workspace de teste pode servir como um local estável, separado do ambiente de desenvolvimento, para realização do UAT (teste de aceitação do usuário) antes da liberação em produção.

Se o conteúdo tiver sido publicado em um workspace na capacidade Premium, [pipelines de implantação](../create-reports/deployment-pipelines-overview.md) poderão simplificar o processo de implantação nos workspaces de desenvolvimento, de teste e de produção. Como alternativa, a publicação pode ser feita manualmente ou por meio de [scripts do PowerShell](https://powerbi.microsoft.com/blog/duplicating-workspaces-by-using-power-bi-cmdlets/).

### <a name="deploy-to-test-workspace"></a>Implantar no workspace de teste

As principais atividades realizadas durante uma implantação no workspace de teste normalmente incluem:

- **Cadeias de conexão e parâmetros:** Ajuste as cadeias de conexão do conjunto de dados se a fonte de dados for diferente entre os ambientes de desenvolvimento e de teste. A [parametrização](../connect-data/service-parameters.md) pode ser usada para gerenciar efetivamente as cadeias de conexão.
- **Conteúdo do workspace:** Publique os conjuntos de dados e os relatórios no workspace de teste e crie dashboards.
- **Aplicativo.** Publique um [aplicativo](../consumer/end-user-apps.md) usando o conteúdo do workspace de teste se ele fizer parte do processo UAT. Normalmente, as permissões do aplicativo são restritas a um número reduzido de pessoas envolvidas com o UAT.
- **Atualização de dados:** [Agende a atualização](../connect-data/refresh-scheduled-refresh.md) de qualquer conjunto de dados de importação para o período em que o UAT estiver ocorrendo.
- **Segurança:** Atualize ou verifique as [funções do workspace](../collaborate-share/service-new-workspaces.md#roles-in-the-new-workspaces). O teste de acesso ao workspace inclui um número reduzido de pessoas que estão envolvidas com o UAT.

> [!NOTE]
> Para obter mais informações sobre as opções de implantação nos ambientes de desenvolvimento, de teste e de produção, consulte a Seção 9 do [white paper de Planejamento de uma implantação empresarial do Power BI](https://aka.ms/PBIEnterpriseDeploymentWP).

### <a name="conduct-user-acceptance-testing"></a>Realizar teste de aceitação do usuário

Em geral, o UAT envolve usuários de negócios que são especialistas no assunto. Após a verificação, eles fornecem a aprovação de que o novo conteúdo é preciso, atende aos requisitos estabelecidos e pode ser implantado para um consumo mais amplo pelos demais.

O nível de formalidade desse processo de UAT, incluindo as aprovações escritas, dependerá das suas práticas de gerenciamento de alterações.

## <a name="deploy-to-production-environment"></a>Implantar no ambiente de produção

Há várias considerações para a implantação no ambiente de produção.

### <a name="conduct-a-staged-deployment"></a>Realizar uma implantação em estágios

Se estiver tentando minimizar os riscos e a interrupção do usuário ou se houver outras preocupações, você poderá optar por executar uma implantação em estágios. A primeira implantação em produção pode envolver um grupo menor de usuários piloto. Em uma implantação piloto, os comentários podem ser solicitados ativamente dos usuários piloto.

Expanda as permissões no workspace de produção ou no aplicativo, gradualmente, até que todos os usuários de destino tenham permissão sobre a nova solução do Power BI.

> [!TIP]
> Use o [Log de Atividades do Power BI](../admin/service-admin-auditing.md) para entender como os consumidores estão adotando e usando a nova solução do Power BI.

### <a name="handle-additional-components"></a>Gerenciar componentes adicionais

Durante o processo de implantação, talvez seja necessário trabalhar com seus administradores do Power BI para resolver outros requisitos que são necessários para dar suporte à solução completa, como:

- **Manutenção do gateway:** pode ser necessário o registro de uma [nova fonte de dados](../connect-data/service-gateway-data-sources.md) no gateway de dados.
- **Drivers e conectores de gateway:** uma nova fonte de dados proprietária pode exigir a instalação de um novo driver ou conector personalizado em cada servidor no cluster de gateway.
- **Criar uma nova capacidade Premium:** você pode ser capaz de usar uma [capacidade Premium](../admin/service-premium-capacity-manage.md) existente. Ou pode haver situações em que uma nova capacidade Premium é garantida. Pode ser o caso quando você deseja separar uma carga de trabalho departamental intencionalmente.
- **Definir um fluxo de dados do Power BI:** as atividades de preparação de dados podem ser configuradas uma vez em um [fluxo de dados do Power BI](../transform-model/service-dataflows-overview.md) usando o Power Query online. Isso ajuda a evitar a replicação do trabalho de preparação de dados em vários arquivos diferentes do Power BI Desktop.
- **Registrar um novo visual organizacional:** o registro do [Visual organizacional](../developer/visuals/power-bi-custom-visuals-organization.md) pode ser feito no portal de administração para visuais personalizados, que não foram originados no AppSource.
- **Definir conteúdo em destaque:** existe uma configuração de locatário que controla quem pode [destacar conteúdo](https://powerbi.microsoft.com/blog/promote-your-reports-dashboards-and-apps-on-power-bi-home/) no home page de serviço do Power BI.
- **Definir rótulos de confidencialidade:** Todos os [rótulos de confidencialidade](../admin/service-security-data-protection-overview.md) estão integrados com a Proteção de Informações da Microsoft.

### <a name="deploy-to-production-workspace"></a>Implantar no workspace de produção

As principais atividades realizadas durante uma implantação no workspace de produção normalmente incluem:

- **Gerenciamento de alterações:** se necessário, obtenha a aprovação para implantar e comunicar a implantação à população de usuários com o auxílio de suas práticas de gerenciamento de alterações padrão. Pode haver uma janela de gerenciamento de alterações aprovada durante a qual as implantações de produção são permitidas. Normalmente ela é aplicável ao conteúdo gerenciado por TI e com muito menos frequência é aplicável ao conteúdo de autoatendimento.
- **Plano de reversão:** com uma migração, a expectativa é que ela seja a migração de uma nova solução pela primeira vez. Se o conteúdo já existir, é prudente ter um plano para reversão à versão anterior, caso seja necessário. Ter versões anteriores dos arquivos do Power BI Desktop (usando o controle de versões do SharePoint ou do OneDrive) funciona bem para essa finalidade.
- **Cadeias de conexão e parâmetros:** ajuste as cadeias de conexão do conjunto de dados quando a fonte de dados for diferente entre os ambientes de teste e de produção. A [parametrização](../connect-data/service-parameters.md) pode ser usada com eficiência para essa finalidade.
- **Atualização de dados:** [agende a atualização do conjunto de dados](../connect-data/refresh-scheduled-refresh.md) para qualquer conjunto de dados importado.
- **Conteúdo do workspace:** publique os conjuntos de dados e os relatórios no workspace de produção e crie os dashboards. Os [pipelines de implantação](../create-reports/deployment-pipelines-overview.md) podem simplificar o processo de implantação nos workspaces de desenvolvimento, de teste e de produção se o conteúdo tiver sido publicado em workspaces na capacidade Premium.
- **Aplicativo:** se os aplicativos fizerem parte da sua estratégia de distribuição de conteúdo, publique um [aplicativo](../consumer/end-user-apps.md) usando o conteúdo do workspace de produção.
- **Segurança:** atualize e verifique as [funções do workspace](../collaborate-share/service-new-workspaces.md#roles-in-the-new-workspaces) com base na sua estratégia de distribuição de conteúdo e de colaboração.
- **Configurações do conjunto de dados:** atualize e verifique as configurações para cada conjunto de dados, incluindo:
  - [endosso](../connect-data/service-datasets-certify.md) (como certificado ou promovido)
  - Conexão de gateway ou credenciais de fonte de dados
  - Atualização agendada
  - [Perguntas e respostas em destaque](../create-reports/service-q-and-a-create-featured-questions.md)
- **Configurações de relatórios e dashboards:** atualize e verifique as configurações para cada relatório e dashboard. As configurações mais importantes incluem:
  - Descrição
  - Grupo ou pessoa de contato
  - [Rótulo de confidencialidade](../admin/service-security-apply-data-sensitivity-labels.md)
  - [Conteúdo em destaque](https://powerbi.microsoft.com/blog/promote-your-reports-dashboards-and-apps-on-power-bi-home/)
- **Assinaturas:** configure assinaturas do relatório, se necessário.

> [!IMPORTANT]
> Neste ponto, você alcançou um grande marco. Comemore sua conquista ao concluir a migração.

### <a name="communicate-with-users"></a>Comunicar-se com os usuário

Anuncie a nova solução aos consumidores. Informe a eles onde podem encontrar o conteúdo, bem como a documentação, as perguntas frequentes e os tutoriais associados. Para apresentar o novo conteúdo, considere a possibilidade de organizar uma sessão de aprendizado durante um almoço ou prepare alguns vídeos sob demanda.

Verifique se incluiu instruções sobre como solicitar ajuda, bem como fornecer comentários.

### <a name="conduct-a-retrospective"></a>Realizar uma retrospectiva

Considere a possibilidade de realizar uma retrospectiva para examinar o que deu certo na migração e o que pode ser feito melhor da próxima vez.

## <a name="run-in-parallel"></a>Executar em paralelo

Em muitas situações, a nova solução será executada em paralelo à solução herdada por um tempo predeterminado. As vantagens de executar em paralelo incluem:

- Redução de riscos, especialmente se os relatórios forem considerados críticos.
- Fornece tempo aos usuários para se acostumarem com a nova solução do Power BI.
- Permite que as informações apresentadas no Power BI sejam cruzadas com os relatórios herdados.

## <a name="decommission-the-legacy-report"></a>Desativar o relatório herdado

Em algum momento, os relatórios migrados para o Power BI devem ser desabilitados na plataforma de BI herdada. A desativação de relatórios herdados pode ocorrer quando:

- O tempo predeterminado para execução em paralelo (que deve ser comunicado à população de usuários) houver expirado. É normalmente de 30 a 90 dias.
- Todos os usuários do sistema herdado tiverem acesso à nova solução do Power BI.
- Não houver mais atividades significativas ocorrendo no relatório herdado.
- Não houver nenhum problema com a nova solução do Power BI que possa afetar a produtividade do usuário.

## <a name="monitor-the-solution"></a>Monitorar a solução

Os eventos do [log de atividades do Power BI](../admin/service-admin-auditing.md) podem ser usados para entender os padrões de uso da nova solução (ou o [log de execução](/sql/reporting-services/report-server/report-server-executionlog-and-the-executionlog3-view) para conteúdo implantado no Servidor de Relatórios do Power BI). A análise do log de atividades pode ajudar a determinar se o uso real difere das expectativas. Também pode validar se a solução tem o suporte adequado.

Aqui estão algumas perguntas que podem ser respondidas examinando o log de atividades:

- Com que frequência o conteúdo está sendo exibido?
- Quem está exibindo o conteúdo?
- O conteúdo normalmente é exibido por meio de um aplicativo ou de um workspace?
- A maioria dos usuários está usando um navegador ou aplicativo móvel?
- As assinaturas estão sendo usadas?
- Há relatórios sendo criados com base nesta solução?
- O conteúdo está sendo atualizado com frequência?
- Como a segurança é definida?
- Há problemas ocorrendo regularmente, como falhas na atualização dos dados?
- Há atividades preocupantes acontecendo (por exemplo, atividades de exportação significativas ou vários compartilhamentos de relatórios individuais) que poderiam indicar a necessidade de treinamento adicional?

> [!IMPORTANT]
> Verifique se alguém pode examinar o log de atividades regularmente. Simplesmente capturá-lo e armazenar o histórico tem valor para fins de auditoria ou de conformidade. No entanto, o valor real é agregado quando uma ação proativa pode ser executada.

## <a name="support-the-solution"></a>Fornecer suporte à solução

Embora a migração esteja concluída, o período após a migração é essencial para abordar problemas e lidar com eventuais preocupações de desempenho. Com o tempo, a solução migrada provavelmente sofrerá alterações à medida que as necessidades de negócios evoluírem.

O suporte tende a ocorrer de maneira um pouco diferente dependendo de como o BI de autoatendimento é gerenciado pela organização. Os defensores do Power BI em todas as unidades de negócios geralmente atuam como um suporte de primeira linha. Embora seja uma função informal, ela é essencial e deve ser incentivada.

Ter um processo de suporte formal, composto pela equipe de TI com base nos tíquetes de suporte, também é algo essencial para lidar com as solicitações de rotina orientadas ao sistema e para fins de escalonamento.

Você também pode ter um [COE (Centro de Excelência)](center-of-excellence-establish.md) que funciona como consultores internos que dão suporte, instruem e gerenciam o Power BI na organização. Um COE pode ser responsável por organizar o conteúdo útil do Power BI em um portal interno.

Por fim, deve estar claro para os consumidores de conteúdo quem contatar em caso de dúvidas sobre o conteúdo e deve haver um mecanismo para fornecer comentários sobre os problemas ou as melhorias.

## <a name="next-steps"></a>Próximas etapas

No [artigo final desta série](powerbi-migration-learn-from-customers.md), aprenda com os clientes ao migrar para o Power BI.

Outros recursos úteis incluem:

- [Transformação de BI da Microsoft](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [White paper de Planejamento de uma implantação empresarial do Power BI](https://aka.ms/PBIEnterpriseDeploymentWP)
- Dúvidas? [Experimente perguntar à Comunidade do Power BI](https://community.powerbi.com/)
- Sugestões? [Contribuir com ideias para aprimorar o Power BI](https://ideas.powerbi.com/)

Parceiros experientes do Power BI estão disponíveis para ajudar sua organização a alcançar sucesso no processo de migração. Para envolver um parceiro do Power BI, visite o [portal de parceiro de Power BI](https://powerbi.microsoft.com/partners/).
