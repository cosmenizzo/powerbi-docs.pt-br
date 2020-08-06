---
title: Definir tabelas em destaque no Power BI Desktop (versão prévia)
description: Crie tabelas em destaque no Power BI Desktop para que elas sejam exibidas na Galeria de Tipos de Dados no Excel.
author: maggiesMSFT
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 07/30/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: c74c618eb4c748d94260573c1ddd4266d3cf5c0e
ms.sourcegitcommit: d9d67ee47954379c2df8db8d0dc8302de4c9f1e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "87478074"
---
# <a name="set-featured-tables-in-power-bi-desktop-preview"></a>Definir tabelas em destaque no Power BI Desktop (versão prévia)

Na Galeria de Tipos de Dados do Excel, seus usuários podem encontrar dados das *tabelas em destaque* em seus conjuntos de dados do Power BI. Neste artigo, você aprende a configurar tabelas como *em destaque* em seus conjuntos de dados. Com essas marcas, seus usuários têm mais facilidade para adicionar dados corporativos a suas planilhas do Excel. Confira as etapas básicas para definir e compartilhar tabelas em destaque.

1. Identifique as tabelas em destaque em seus conjuntos de dados no Power BI Desktop (este artigo)
1. Salve esses conjuntos de dados com as tabelas em destaque em um dos novos workspaces. Os criadores de relatório podem criar relatórios com essas tabelas em destaque. 
1. O restante da organização pode se conectar às tabelas em destaque, chamadas de *tipos de dados* no Excel, para obter dados relevantes e atualizáveis. O artigo [Acessar tabelas em destaque do Power BI no Excel (versão prévia)](service-excel-featured-tables.md) descreve o consumo dessas tabelas no Excel.

> [!NOTE]
> É possível [promover ou certificar conjuntos de dados no Power BI](../connect-data/service-datasets-promote.md). Isso é chamado de *endosso*. O Excel prioriza as tabelas em conjuntos de dados endossados na Galeria de Tipos de Dados. O Excel lista as tabelas em destaque em conjuntos de tabela certificados primeiro e depois as tabelas em conjuntos de dados promovidos. O Excel lista, em seguida, as tabelas em destaque em conjuntos de dados não endossados. 

## <a name="turn-on-the-featured-table-preview"></a>Ativar a versão preliminar da tabela em destaque

1. No Power BI Desktop, selecione **Arquivo** > **Opções e Configurações** > **Opções** > **Versão Prévia dos Recursos**.
2. Marque a caixa de seleção **Tabelas em destaque**.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-preview-featured-tables.png" alt-text="Opção Versão prévia das tabelas em destaque":::

3. Reinicie o Power BI Desktop.

## <a name="select-a-table"></a>Selecionar uma tabela

1. No Power BI Desktop, vá para Exibição de modelo.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-model-view.png" alt-text="Exibição de modelo":::
 
2. Selecione uma tabela e defina **É tabela em destaque** para **Sim**.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-featured-table-yes.png" alt-text="Definir É tabela em destaque como Sim":::

4. Em **Configurar esta tabela em destaque**, forneça os campos obrigatórios:

    - Uma **Descrição**. 
        > [!TIP]
        > Inicie a descrição com "Tabela em destaque" para ajudar os criadores de relatórios do Power BI a identificarem essas tabelas.
    - O valor do campo **Rótulo de linha** é usado no Excel para que os usuários possam identificar facilmente a linha. Ele aparece como o valor da célula de uma célula vinculada, no painel **Seletor de Dados** e no cartão **Informações**. 
    - O valor do campo **Coluna de chave** fornece a ID exclusiva para a linha. Esse valor permite que o Excel vincule uma célula a uma linha específica na tabela.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-set-up-featured-table.png" alt-text="Configurar tabela em destaque":::

1. Após você publicar ou importar o conjunto de dados para a serviço do Power BI, a tabela em destaque é exibida na Galeria de Tipos de Dados do Excel. Você e outros criadores de relatórios também podem criar relatórios com base nesse conjunto de dados.

1. No Excel: 
    - O Excel armazena em cache a lista de tipos de dados, portanto, é necessário reiniciar o Excel para ver as tabelas em destaque publicadas recentemente.
    - Alguns conjuntos de dados não têm suporte na versão preliminar, as tabelas em destaque definidas neles não aparecerão no Excel. Confira os detalhes na próxima seção, Considerações e limitações.

## <a name="considerations-and-limitations"></a>Considerações e limitações

Estas são as limitações da versão prévia inicial.

- As tabelas em destaque em conjuntos de dados do Power BI que usam os seguintes recursos não são mostradas no Excel: 

    - Conjuntos de dados de segurança em nível de linha.
    - Conjuntos de dados habilitados da Proteção de Informações da Microsoft.
    - Conjuntos de dados do DirectQuery.
    - Conjuntos de dados com uma conexão dinâmica.

- O Excel mostra somente os dados em colunas e colunas calculadas na tabela em destaque. Os itens a seguir não são fornecidos na versão preliminar inicial:

    - Medidas definidas na tabela de recursos.
    - Medidas definidas em tabelas relacionadas e medidas implícitas calculadas de relações.

- O Excel exibe somente tabelas em destaque armazenadas nos novos workspaces do Power BI. Tabelas em destaque armazenadas nos workspaces clássicos, ou em Meu Workspace, não são mostradas como tipos de dados no Excel. Você pode [atualizar workspaces clássicos para os novos workspaces](service-upgrade-workspaces.md) no Power BI.
- Confira [Considerações e limitações](service-excel-featured-tables.md#considerations-and-limitations) no artigo "Acessar tabelas em destaque do Power BI no Excel" para ver outras considerações sobre o Excel.

## <a name="next-steps"></a>Próximas etapas

- [Acessar tabelas em destaque do Power BI no Excel](service-excel-featured-tables.md)
- Leia mais sobre como [usar tipos de dados do Excel por meio do Power BI](https://support.office.com/article/use-excel-data-types-from-power-bi-preview-cd8938ce-f963-444d-b82a-7140848241e9) na documentação do Excel.
- Dúvidas? [Experimente a Comunidade do Power BI](https://community.powerbi.com/)

