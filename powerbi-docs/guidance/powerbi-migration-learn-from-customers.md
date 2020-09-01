---
title: Aprender com as migrações dos clientes para o Power BI
description: Aprenda com os clientes ao migrar para o Power BI.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/20/2020
ms.author: v-pemyer
ms.openlocfilehash: a725d2763d7d044220785c2f9727ee30f14bfd5d
ms.sourcegitcommit: 84e75a2cd92f4ba4e0c08ba296b981b79d6d0e82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88803114"
---
# <a name="learn-from-customer-power-bi-migrations"></a>Aprender com as migrações dos clientes para o Power BI

Este artigo, que conclui a série sobre migração para o Power BI, compartilha as principais lições aprendidas por dois clientes que migraram com sucesso para o Power BI.

## <a name="international-consumer-goods-company"></a>Empresa de bens de consumo internacional

Uma empresa de bens de consumo internacional, que vende centenas de produtos, tomou a decisão em 2017 de buscar uma estratégia prioritariamente de nuvem. Um dos principais fatores para seleção do Power BI como a plataforma de BI (business intelligence) escolhida é a profunda integração com o Azure e o Microsoft 365.

### <a name="conduct-a-phased-migration"></a>Realizar uma migração em fases

Em 2017, a empresa começou a usar o Power BI. O objetivo organizacional inicial era introduzir o Power BI como uma ferramenta de BI adicional. A decisão forneceu aos criadores de conteúdo, consumidores e ao departamento de TI o tempo de adaptação a novas maneiras de entregar o BI. Também permitiu que eles adquirissem conhecimentos sobre o Power BI.

Durante a segunda metade de 2018, um anúncio formal foi feito declarando que o Power BI havia sido a ferramenta de BI aprovada para a organização. E, portanto, todo novo trabalho de desenvolvimento de BI deveria ocorrer no Power BI. A disponibilidade do Power BI Premium foi um fator essencial para tomada dessa decisão. Neste momento, a organização desencorajava o uso da antiga plataforma de BI e o planejamento da transição foi iniciado.

Até o final de 2019, começou o trabalho para migrar o conteúdo existente da plataforma de BI herdada para o Power BI. Alguns dos usuários pioneiros migraram o conteúdo deles rapidamente. Isso ajudou o Power BI a ganhar ainda mais impulso em toda a organização. Então, foi solicitado aos proprietários e criadores de conteúdo que começassem a se preparar para migrar totalmente para o Power BI até o final de 2020. A organização ainda enfrenta desafios relacionados a habilidades, tempo e financiamento, embora nenhum desses desafios esteja relacionado à própria plataforma de tecnologia.

> [!IMPORTANT]
> O Power BI já havia se tornado um sucesso e conquistado espaço dentro da organização antes mesmo da solicitação às unidades de negócios para adotar esforços de migração formal a fim de deixar a antiga plataforma de BI.

### <a name="prepare-to-handle-varying-responses"></a>Preparar para lidar com as diferentes respostas

Nessa grande organização descentralizada, havia diferentes níveis de receptividade e disposição para migrar para o Power BI. Além das preocupações relacionadas a tempo e orçamento, havia funcionários que fizeram investimentos significativos no desenvolvimento de habilidades na antiga plataforma de BI. Portanto, o anúncio sobre tornar o Power BI a ferramenta padrão não era uma notícia bem recebida por todos. Como cada unidade de negócios tem seu orçamento próprio, elas podem questionar decisões como esta. À medida que as decisões sobre as ferramentas de TI foram tomadas de maneira centralizada, isso gerou alguns desafios a serem tratados pelo patrocinador executivo e os líderes de BI.

> [!IMPORTANT]
> A comunicação com as equipes de liderança em todas as unidades de negócios era essencial para garantir que todos compreendiam os benefícios organizacionais de alto nível da adoção do Power BI como a ferramenta padrão de BI. Uma comunicação eficaz tornou-se ainda mais essencial à medida que a migração evoluía e a data de encerramento da plataforma de BI herdada se aproximava.

### <a name="focus-on-the-bigger-picture"></a>Foco no panorama geral

A empresa descobriu que, embora alguns relatórios migrados pudessem replicar o design original de modo seguro, nem todos os relatórios individuais poderiam ser reproduzidos com fidelidade no Power BI. Embora isso fosse algo esperado, já que todas as plataformas de BI são diferentes. revelou que era necessária uma mentalidade de design diferente.

Foram fornecidas diretrizes para os criadores de conteúdo: foco na criação de relatórios para fins específicos no Power BI, em vez de tentar chegar a réplicas exatas dos relatórios herdados. Por esse motivo, os especialistas no assunto precisam estar ativamente disponíveis para consulta e validação durante o processo de migração. Esforços foram empenhados para levar em conta a finalidade do design do relatório e para melhorá-lo quando necessário.

> [!IMPORTANT]
> Às vezes, a melhor abordagem é fazer melhorias durante a migração. Outra vezes, a melhor opção é fornecer exatamente o mesmo valor que antes, sem melhorias significativas, para não prejudicar a linha do tempo de migração.

### <a name="cautiously-assess-priorities"></a>Avaliar com cuidado as prioridades

Foi realizada uma análise da antiga plataforma de BI para entender por completo o uso dela. A antiga plataforma de BI tinha milhares de relatórios publicados, dos quais aproximadamente a metade havia sido acessada no ano anterior. Esse número pode ser cortado na metade mais uma vez ao avaliar quais relatórios foram considerados por fornecer um valor significativo à organização. Esses relatórios foram priorizados na migração.

> [!IMPORTANT]
> É muito fácil superestimar a importância real de um relatório. Para relatórios que não são usados com frequência, avalie se eles podem ser desativados por completo. Às vezes, a coisa mais barata e simples a se fazer é nada.

### <a name="cautiously-assess-complexity"></a>Avaliar com cuidado a complexidade

Dentre os relatórios priorizados, as estimativas de tempo foram compiladas com base nos níveis de esforços estimados: simples, médio ou complexo. Embora pareça um processo relativamente direto, não espere que as estimativas de tempo sejam precisas para cada relatório individual. Você poderá observar estimativas totalmente imprecisas. Por exemplo, a empresa tinha um relatório que considerava altamente complexo. Foi atribuída a ele uma estimativa de conversão de 50 dias pelos consultores. No entanto, o relatório reprojetado no Power BI foi concluído em cerca de 50 horas.

> [!IMPORTANT]
> Embora as estimativas de tempo geralmente sejam necessárias para se obter financiamento e realizar atribuições de pessoal, elas provavelmente são mais valiosas quando consideradas em conjunto.

### <a name="decide-how-change-management-is-handled"></a>Decidir como o gerenciamento de alterações será tratado

Com um volume de ativos de BI tão alto, o gerenciamento de alterações dos relatórios pertencentes à empresa representava um grande desafio. Os relatórios gerenciados por TI foram tratados de acordo com as práticas de gerenciamento de alterações padrão. No entanto, devido ao alto volume, não foi possível promover alterações no conteúdo pertencente à empresa de modo centralizado.

> [!IMPORTANT]
> A responsabilidade adicional recairá sobre as unidades de negócios quando for inviável gerenciar as alterações de uma equipe centralizada.

### <a name="create-an-internal-community"></a>Criar uma comunidade interna

A empresa estabeleceu um COE (Centro de Excelência) para fornecer recursos e aulas de treinamento interno. O COE também serve como um grupo de consultoria interno que está pronto para auxiliar os criadores de conteúdo com problemas técnicos, resolução de obstáculos e diretrizes de melhores práticas.

Há também uma comunidade interna do Power BI que tem se mostrado um grande sucesso, já contando com mais de 1.600 membros. A Comunidade é gerenciada no Yammer. Os membros podem fazer perguntas internamente relevantes e receber respostas que respeitam as melhores práticas e as restrições organizacionais. Esse tipo de interação entre usuários alivia grande parte da carga de suporte do COE. No entanto, o COE monitora as perguntas e respostas e participa das conversas quando necessário.

Uma extensão da comunidade interna é a nova rede de especialistas do Power BI. Ela inclui um pequeno número de defensores do Power BI selecionados previamente de dentro da organização. Eles são profissionais das unidades de negócios altamente qualificados no Power BI, além de defensores entusiasmados que desejam atuar ativamente para resolver os desafios da empresa. Os membros da rede de especialistas do Power BI devem obedecer às melhores práticas e diretrizes estabelecidas pelo COE e ajudar a comunidade interna mais ampla do Power BI a entendê-las e implementá-las. Embora a rede de especialistas do Power BI colabore com o COE e possa receber treinamento dedicado, os especialistas do Power BI operam de maneira independente do COE. Cada especialista do Power BI pode definir os parâmetros de como eles funcionam, tendo em mente que eles têm outras responsabilidades e prioridades em sua função oficial.

> [!IMPORTANT]
> Ter um escopo bem definido a respeito do que o COE faz, como: adoção, governança, diretrizes, melhores práticas, treinamentos, suporte e, talvez, até mesmo desenvolvimento prático. Embora um COE seja incrivelmente valioso, pode ser difícil medir seu retorno sobre o investimento.

### <a name="monitor-migration-progress-and-success"></a>Monitorar o progresso e o sucesso da migração

Os KPIs (indicadores chave de desempenho) são monitorados continuamente durante a migração para o Power BI. Eles ajudam a empresa a compreender as tendências de métricas, como o número de visitas de relatório e o número de relatórios ativos e de usuários distintos por mês. O aumento do uso do Power BI é medido paralelamente à redução do uso da antiga plataforma de BI, com o objetivo de alcançar uma relação inversa. Os destinos são atualizados a cada mês para se adaptar às alterações. Se o uso não estiver ocorrendo no ritmo desejado, os gargalos deverão ser identificados para que ações apropriadas possa ser adotadas.

> [!IMPORTANT]
> Crie um scorecard de migração com business intelligence acionável para monitorar o sucesso dos esforços de migração.

## <a name="large-transportation-and-logistics-company"></a>Grande empresa de transporte e logística

Uma grande empresa de transporte e logística da América do Norte está investindo ativamente na modernização da infraestrutura de dados e dos sistemas analíticos dela.

### <a name="allow-a-period-of-gradual-growth"></a>Permitir um período de crescimento gradual

A empresa começou a usar o Power BI em 2018. Em meados de 2019, o Power BI já havia se tornado a plataforma preferida para todos os novos casos de uso de BI. Então, em 2020, a empresa se concentrou na desativação gradual da plataforma de BI existente, além de uma série de soluções de BI do ASP.NET personalizadas.

> [!IMPORTANT]
> O Power BI tinha muitos usuários ativos em toda a organização antes de começar a desativação gradual de suas soluções e plataformas de BI herdadas.

### <a name="balance-centralized-and-distributed-groups"></a>Equilibrar grupos centralizados e distribuídos

Na empresa, há dois tipos de equipes de BI: a equipe central de BI e os grupos de análise distribuídos ao longo de toda a organização. A equipe central de BI tem a responsabilidade de propriedade do Power BI enquanto plataforma, mas não tem nenhum conteúdo em si. Dessa forma, a equipe central de BI é um hub de habilitação técnica que dá suporte aos grupos de análise distribuídos.

Cada um dos grupos de análise é dedicado a uma unidade de negócios específica ou a uma função de serviços compartilhados. Um pequeno grupo pode conter um único analista, ao passo que um grupo maior pode ter de 10 a 15 analistas.

> [!IMPORTANT]
> Os grupos de análise distribuídos incluem especialistas no assunto que estão familiarizados com as necessidades de negócios cotidianas. Essa separação permite que a equipe central de BI se concentre principalmente na habilitação técnica e no suporte dos serviços e das ferramentas de BI.

### <a name="focus-on-dataset-reusability"></a>Foco na reutilização do conjunto de dados

A dependência de soluções de BI do ASP.NET personalizadas era uma barreira para o desenvolvimento de novas soluções de BI. O conjunto de habilidades necessário fazia com que o número de criadores de conteúdo de autoatendimento fosse reduzido. Como o Power BI é uma ferramenta muito mais acessível, especificamente projetada para o autoatendimento de BI, ela se disseminou rapidamente por toda a organização após sua liberação.

A capacitação dos analistas de dados dentro da empresa gerou resultados positivos imediatos. No entanto, o foco inicial do desenvolvimento de Power BI foi a visualização. Embora isso tenha resultado em soluções de BI valiosas, esse foco resultou em um grande número de arquivos do Power BI Desktop, cada qual com uma relação um-para-um entre o relatório e o conjunto de dados correspondente. Isso resultou em muitos conjuntos de dados e na duplicação de dados e da lógica de negócios. Para reduzir a duplicação de dados, lógica e esforços, a empresa forneceu treinamento e suporte aos criadores de conteúdo.

> [!IMPORTANT]
> Inclua informações sobre a importância da reutilização de dados em seus esforços de treinamento interno. Aborde os conceitos importantes o mais cedo possível.

### <a name="test-data-access-multiple-ways"></a>Testar o acesso a dados de várias maneiras

A plataforma de data warehouse da empresa é a DB2. Com base no design de data warehouse atual, a empresa descobriu que os modelos DirectQuery funcionaram melhor para seus requisitos, em vez dos modelos de importação.

> [!IMPORTANT]
> Realize uma prova de conceito técnica para avaliar o modo de armazenamento de modelo que funciona melhor. Além disso, ensine os modeladores de dados sobre os modos de armazenamento de modelo e como eles podem escolher um modo apropriado para os projetos deles.

### <a name="educate-authors-about-premium-licensing"></a>Instruir os criadores de conteúdo sobre o licenciamento Premium

Como foi mais fácil começar a usar o Power BI (em comparação com a plataforma de BI herdada), muitos dos pioneiros foram pessoas que não tinham uma licença para a ferramenta de BI anterior. Conforme esperado, o número de criadores de conteúdo cresceu consideravelmente. Esses criadores de conteúdo queriam compartilhar o conteúdo criado com outras pessoas, o que gerou uma necessidade contínua de licenças adicionais do Power BI Pro.

A empresa fez um grande investimento em workspaces Premium, mais notavelmente para distribuir conteúdo do Power BI a inúmeros usuários que tinham licenças gratuitas do Power BI. A equipe de suporte trabalha com os criadores de conteúdo para verificar se eles usam os workspaces Premium apenas quando necessário. Isso evita a alocação desnecessária de licenças do Power BI Pro quando um usuário só precisa consumir conteúdo.

> [!IMPORTANT]
> Muitas vezes surgem perguntas sobre licenciamento. Esteja preparado para instruir e ajudar os criadores de conteúdo a abordar as perguntas sobre licenciamento. Verifique se as solicitações do usuário por licenças do Power BI Pro são justificáveis.

### <a name="understand-the-data-gateways"></a>Entender o gateway de dados

No início, a empresa tinha muitos gateways pessoais. O uso de um cluster de gateway de dados local muda os esforços de gerenciamento para a equipe central de BI, o que permite à comunidade de criadores de conteúdo se concentrar na produção de conteúdo. A equipe central de BI trabalhou com a comunidade interna de usuários do Power BI para reduzir o número de gateways pessoais.

> [!IMPORTANT]
> Tenha um plano para criar e gerenciar os gateways de dados locais. Decida quem tem permissão para instalar e usar um gateway pessoal e aplicá-lo por meio de políticas de gateway.

### <a name="formalize-your-support-plan"></a>Formalizar o plano de suporte

À medida que a adoção do Power BI cresceu na organização, a empresa percebeu que uma abordagem de suporte com várias camadas funcionaria bem:

- **Camada 1: Dentro da equipe:** as pessoas aprendem e ensinam umas às outras todos os dias.
- **Camada 2: Comunidade do Power BI:** as pessoas fazem perguntas sobre a comunidade de equipes internas para aprender umas com as outras e comunicar informações importantes.
- **Camada 3: Equipe central de BI e COE:** as pessoas enviam solicitações por email para obter assistência. As sessões em _horário comercial_ são realizadas duas vezes por semana para discutir os problemas e compartilhar as ideias entre todos os membros.

> [!IMPORTANT]
> Embora as duas primeiras camadas sejam menos formais, elas são tão importantes quanto a terceira camada de suporte. Usuários experientes tendem a confiar principalmente nas pessoas que eles conhecem, enquanto os usuários mais novos (ou aqueles que são o único analista de dados de uma unidade de negócios ou de um serviço compartilhado) tendem a confiar mais no suporte formal.

### <a name="invest-in-training-and-governance"></a>Investir em treinamento e governança

No ano passado, a empresa melhorou suas ofertas de treinamento interno e aperfeiçoou seu programa de governança de dados. O Comitê de governança inclui os principais membros de cada um dos grupos de análise distribuídos, além do COE.

Atualmente, há seis cursos internos do Power BI em seu catálogo interno. O curso [Dashboard em um dia](https://powerbi.microsoft.com/diad/) continua sendo um curso bastante popular entre os iniciantes. Para ajudar os usuários a aprofundar suas habilidades, eles fornecem uma série de três cursos do Power BI e dois cursos do DAX.

Uma das decisões de governança de dados mais importantes está relacionada ao gerenciamento de capacidades Premium. A empresa optou por alinhar a capacidade dedicada dela às principais áreas de análise das unidades de negócios e dos serviços compartilhados. Portanto, se houver ineficiências, o impacto será apenas dentro dessa área e os administradores de capacidade descentralizados serão capacitados para gerenciar a capacidade da maneira como quiserem.

> [!IMPORTANT]
> Preste atenção ao modo como as capacidades Premium são usadas e como os workspaces são atribuídos a elas.

## <a name="next-steps"></a>Próximas etapas

Outros recursos úteis incluem:

- [Transformação de BI da Microsoft](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [White paper de Planejamento de uma implantação empresarial do Power BI](https://aka.ms/PBIEnterpriseDeploymentWP)
- [Dashboard em um dia](https://powerbi.microsoft.com/diad/)
- Dúvidas? [Experimente perguntar à Comunidade do Power BI](https://community.powerbi.com/)
- Sugestões? [Contribuir com ideias para aprimorar o Power BI](https://ideas.powerbi.com/)

Parceiros experientes do Power BI estão disponíveis para ajudar sua organização a alcançar sucesso no processo de migração. Para envolver um parceiro do Power BI, visite o [portal de parceiro de Power BI](https://powerbi.microsoft.com/partners/).
