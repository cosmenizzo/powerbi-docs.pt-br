---
title: Clientes do Power BI for US Government – Visão geral
description: Os clientes do Power BI for US Government podem adicionar uma assinatura do Power BI Pro ao plano do Microsoft 365 Government. Saiba como se inscrever e examinar a disponibilidade de recursos nesta descrição de serviço.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/02/2020
ms.author: kfollis
ms.custom: licensing support
LocalizationGroup: Get started
ms.openlocfilehash: 2b5481e3d0b84f81a9cdee827df27c90e32a7e84
ms.sourcegitcommit: ae9e698b082598f37242080a3ad3dd0b3be08478
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2020
ms.locfileid: "89474780"
---
# <a name="power-bi-for-us-government-customers"></a>Clientes do Power BI for US Government

Este artigo se destina aos clientes do Governo dos EUA que estão implantando o Power BI como parte de um plano do Microsoft 365 Government. Os planos governamentais são projetados para as necessidades exclusivas das organizações que devem atender aos padrões de conformidade e segurança dos EUA. O serviço do Power BI projetado para os clientes do Power BI for US Government é diferente da versão comercial do serviço do Power BI. As funcionalidades e diferenças do recurso estão descritas nas seções a seguir.

## <a name="add-power-bi-to-your-microsoft-365-government-plan"></a>Adicionar o Power BI ao seu plano do Microsoft 365 Government

Antes de obter uma assinatura do Power BI US Government e atribuir licenças aos usuários, é preciso se inscrever em um plano do Microsoft 365 Government. Caso sua organização já tenha um plano do Microsoft 365 Government, passe para [Comprar uma assinatura do Power BI Pro para clientes do governo](#buy-a-power-bi-pro-subscription-for-government-customers).

### <a name="enroll-in-a-microsoft-365-government-plan"></a>Registrar-se em um plano do Microsoft 365 Government

Se você for um novo cliente, terá que validar a qualificação da sua organização antes de se inscrever em um plano do Microsoft 365 Government.  Comece preenchendo o [formulário de validação de qualificação do Microsoft 365 para a Administração Pública](https://www.microsoft.com/microsoft-365/government/eligibility-validation). Para garantir que você esteja selecionando o plano adequado para sua organização, confira as [descrições do serviço do Microsoft 365 US Government](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government).

> [!NOTE]
> Se você já tiver implantado o Power BI em um ambiente comercial e quiser migrar para a nuvem do governo dos EUA, será preciso adicionar uma nova assinatura do Power BI Pro a seu plano do Microsoft 365 Government. Em seguida, replique os dados comerciais no serviço do Power BI for US Government, remova as atribuições de licença comercial das contas de usuário e atribua a elas uma licença governamental do Power BI Pro.
>
>
### <a name="buy-a-power-bi-pro-subscription-for-government-customers"></a>Comprar uma assinatura do Power BI Pro para clientes do governo

Depois de implantar o Microsoft 365, será possível adicionar uma assinatura do Power BI Pro. Siga as instruções passo a passo em [Registrar sua organização do Governo dos EUA](service-govus-signup.md) para comprar o serviço do Power BI Pro Government. Compre licenças suficientes para todos os usuários que precisam usar o Power BI e as atribua às contas de usuário individuais.

> [!IMPORTANT]
> O Power BI for US Government não está disponível como uma licença *gratuita*. Para acessar a Nuvem da Comunidade Governamental, cada usuário deve ter atribuído uma licença *Pro*. Se uma conta de usuário tiver uma licença gratuita atribuída, o usuário estará autorizado a acessar apenas a nuvem comercial e encontrará problemas de autenticação e de acesso. Se você comprou o Power BI Premium, não precisa atribuir licenças Pro para habilitar o acesso do usuário.  Os usuários na organização podem acessar relatórios compartilhados com eles, desde que o relatório seja publicado em uma capacidade Premium. Examine as diferenças entre os tipos de licença em [Recursos do serviço do Power BI por tipo de licença](../fundamentals/service-features-license-type.md).
>

## <a name="government-cloud-instances"></a>Instâncias de nuvem do governo

O Microsoft 365 fornece diversos ambientes para que as agências governamentais atendam aos vários requisitos de conformidade. Para obter mais informações sobre cada ambiente, confira:

* A [GCC (Nuvem da Comunidade Governamental) do Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc) foi projetada para o governo federal, estadual e local.

* A [GCC High (Nuvem da Comunidade Governamental High) do Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc-high-and-dod) foi projetada para as agências federais, os setores de defesa e aeroespacial e outras organizações que mantêm informações controladas não confidenciais. Esse ambiente é adequado para organizações de segurança nacional e empresas que têm dados ITAR (Normas de Tráfego Internacional de Armas) ou requisitos DFARS (Suplemento do Regulamento de Aquisição Federal para a Defesa).

* O [ambiente do Microsoft 365 DoD](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc-high-and-dod) foi projetado exclusivamente para o Departamento de Defesa dos EUA.

## <a name="connect-to-power-bi-for-us-government"></a>Conexão ao Power BI for US Government

A URL para se conectar ao Power BI difere para usuários do governo e usuários comerciais. Use as seguintes URLs para entrar no Power BI:

| Versão comercial  | GCC  | GCC High | DoD |
| --- | --- | --- | --- |
| [https://app.powerbi.com/](https://app.powerbi.com) |[https://app.powerbigov.us](https://app.powerbigov.us) | [https://app.high.powerbigov.us](https://app.high.powerbigov.us) | [https://app.mil.powerbigov.us](https://app.mil.powerbigov.us) |

Sua conta pode estar configurada em mais de uma nuvem. Se esse for o caso da sua conta, ao entrar no Power BI Desktop, será possível escolher a qual nuvem se conectar.

## <a name="connect-government-and-global-azure-cloud-services"></a>Conectar os Serviços de Nuvem do Azure globais e governamentais

O Azure é distribuído em várias nuvens. Por padrão, a habilitação de regras de firewall para abrir uma conexão com uma instância específica da nuvem é possível, mas a rede entre nuvens é diferente.  Para se comunicar entre serviços na nuvem pública e serviços na Nuvem da Comunidade Governamental, é preciso configurar regras de firewall específicas. Por exemplo, se você quiser acessar instâncias da nuvem pública do banco de dados SQL usando sua implantação da nuvem governamental do Power BI, precisará de uma regra de firewall no banco de dados SQL. Configure regras de firewall específicas para banco de dados SQL a fim de permitir conexões à Nuvem do Azure Governamental para os seguintes data centers:

* Gov. EUA – Iowa
* Gov. EUA – Virgínia
* Gov. EUA – Texas
* Gov. EUA – Arizona

Na nuvem pública, os intervalos de IP estão disponíveis. Baixe o arquivo [Marcas de serviço e intervalos de IP do Azure – Nuvem do Governo dos EUA](https://www.microsoft.com/download/details.aspx?id=57063) para obter os intervalos de IP da Nuvem do Governo dos EUA.

Para configurar firewalls para bancos de dados SQL, confira [Criar e gerenciar regras de firewall de IP](https://docs.microsoft.com/azure/sql-database/sql-database-firewall-configure#create-and-manage-ip-firewall-rules).

## <a name="power-bi-feature-availability"></a>Disponibilidade do recurso do Power BI

Para atender aos requisitos dos clientes de nuvem governamental, existem algumas diferenças entre planos comerciais e governamentais. Nossa meta é disponibilizar todos os recursos em nuvens governamentais em até 30 dias após a disponibilidade geral. Em alguns casos, dependências subjacentes nos impedem de disponibilizar um recurso.

A seguinte tabela lista os recursos que não estão disponíveis em um ambiente governamental específico e a disponibilidade estimada se o lançamento estiver planejado:

|Recurso |GCC |GCC High |DoD|
|------|------|------|------|
|[Colaboração B2B do Azure entre a nuvem comercial e a governamental](service-admin-azure-ad-b2b.md)<sup>1</sup>|![disponível](../media/yes.png)|![não disponível](../media/no.png)|![não disponível](../media/no.png)|
|[Inserção no SharePoint Online usando a Web Part do Power BI](https://docs.microsoft.com/esharepoint/dev/spfx/web-parts/overview-client-side-web-parts)|![disponível](../media/yes.png)|![Disponível](../media/yes.png)|![não disponível](../media/no.png)|
|[Conectividade do Power Automate para alertas controlados por dados](../connect-data/power-bi-data-sources.md)|![disponível](../media/yes.png)|![disponível](../media/yes.png)|![não disponível](../media/no.png)|
|[Guia do Power BI no Teams](../collaborate-share/service-collaborate-microsoft-teams.md)<sup>2</sup>|![disponível](../media/yes.png)|![não disponível](../media/no.png)|![não disponível](../media/no.png)|
|[Métricas de Capacidade](../admin/service-admin-premium-monitor-portal.md)|3º trimestre de 2020 |3º trimestre de 2020|3º trimestre de 2020|
|[Modelos grandes](service-premium-large-models.md) | 4º trimestre de 2020 |4º trimestre de 2020| ![não disponível](../media/no.png) |
|[Fluxos de dados – otimização do mecanismo de Computação do SQL](../transform-model/service-dataflows-enhanced-compute-engine.md) | 4º trimestre de 2020 |4º trimestre de 2020| ![não disponível](../media/no.png) |
|[Fluxos de dados – Consulta Direta](../transform-model/service-dataflows-directquery.md) | 4º trimestre de 2020 |4º trimestre de 2020|![não disponível](../media/no.png)|
|[Notificações de interrupção de serviço](service-premium-large-models.md)|4º trimestre de 2020 |4º trimestre de 2020|4º trimestre de 2020|
|[Proteção de Dados (rótulos MIP)](service-security-sensitivity-label-overview.md)|4º trimestre de 2020|4º trimestre de 2020 |4º trimestre de 2020|
|[Aplicativos de modelo](../connect-data/service-template-apps-overview.md)<sup>3</sup>|4º trimestre de 2020 |4º trimestre de 2020| 4º trimestre de 2020|
|[Visuais personalizados](../developer/visuals/power-bi-custom-visuals.md)<sup>3</sup>|4º trimestre de 2020 |4º trimestre de 2020| 4º trimestre de 2020|
|[Geração de Código QR](../create-reports/service-create-qr-code-for-tile.md)|![não disponível](../media/no.png)|![não disponível](../media/no.png)|![não disponível](../media/no.png)|

<sup>1</sup> Embora a Colaboração B2B esteja disponível para GCC, o usuário externo deve receber uma licença nesse ambiente. As licenças de nuvem comercial não são válidas no GCC. Para obter mais informações sobre limitações conhecidas da Colaboração B2B para o governo dos EUA, [compare o Azure Government e o Azure global](https://docs.microsoft.com/azure/azure-government/compare-azure-government-global-azure#azure-active-directory-premium-p1-and-p2)

<sup>2</sup> A experiência de Power BI no Teams para GCC é limitada, funciona apenas para workspaces clássicos e não inclui a funcionalidade aprimorada descrita em [Inserir conteúdo do Power BI no Microsoft Teams](../collaborate-share/service-embed-report-microsoft-teams.md).

<sup>3</sup> A funcionalidade para Aplicativos de Modelo e Visuais Personalizados no lançamento será limitada para as nuvens governamentais. Mais informações sobre limitações específicas serão publicadas no lançamento.

## <a name="next-steps"></a>Próximas etapas

* [Inscrever-se para o Power BI for US Government](service-govus-signup.md)
* [Microsoft Power Apps US Government](https://docs.microsoft.com/power-platform/admin/powerapps-us-government)
* [Power Automate US Government](https://docs.microsoft.com/power-automate/us-govt)
* [Demonstração do governo dos EUA do Power BI](https://channel9.msdn.com/Blogs/Azure/Cognitive-Services-HDInsight-and-Power-BI-on-Azure-Government)
