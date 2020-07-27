---
title: Limitações da entidade de serviço
description: Limitações da entidade de serviço
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 06/06/2020
ms.custom: include file
ms.openlocfilehash: 569d7dfe251183962a14de1c42d85ee2e58950af
ms.sourcegitcommit: d8acf2fb0318708a3e8e1e259cb3747b0312b312
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86401681"
---
## <a name="considerations-and-limitations"></a>Considerações e limitações

* A entidade de serviço só funciona com [novos workspaces](../collaborate-share/service-create-the-new-workspaces.md).
* Não há suporte para **Meu Workspace** ao usar a entidade de serviço.
* É necessária capacidade dedicada ao passar para produção.
* Você não pode entrar no portal do Power BI usando a entidade de serviço.
* Direitos de administrador do Power BI são necessários para habilitar a entidade de serviço nas configurações do desenvolvedor no portal do administrador do Power BI.
* Os aplicativos [inseridos para sua organização](../developer/embedded/embed-sample-for-your-organization.md) não podem usar a entidade de serviço.
* Não há suporte para gerenciamento de [fluxos de dados](../transform-model/service-dataflows-overview.md).
* No momento, a entidade de serviço não dá suporte a nenhuma API de administrador.
* Ao usar uma entidade de serviço com uma fonte de dados do [Azure Analysis Services](https://docs.microsoft.com/azure/analysis-services/analysis-services-overview), a própria entidade de serviço precisa ter permissões de uma instância do Azure Analysis Services. O uso de um grupo de segurança que contenha a entidade de serviço para essa finalidade não funciona.
* No momento, a entidade de serviço não pode acessar fontes de dados no gateway. Ou seja, não é possível adicionar a entidade de serviço como os usuários da fonte de dados no gateway.
