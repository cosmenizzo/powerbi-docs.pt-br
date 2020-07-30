---
title: Acessar tabelas em destaque do Power BI no Excel (versão preliminar)
description: No Excel, você pode encontrar dados de tabelas em destaque em conjuntos de dados do Power BI na Galeria de Tipos de Dados.
author: maggiesMSFT
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 07/24/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 00fba391a6ad92f1e3edaf0e2af9691452724f6e
ms.sourcegitcommit: 65025ab7ae57e338bdbd94be795886e5affd45b4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87251371"
---
# <a name="access-power-bi-featured-tables-in-excel-preview"></a>Acessar tabelas em destaque do Power BI no Excel (versão preliminar)

Na Galeria de Tipos de Dados do Excel, você poderá encontrar dados das *tabelas em destaque* em conjuntos de dados do Power BI. As tabelas em destaque facilitam a adição de dados empresariais a suas planilhas do Excel. Veja a seguir as etapas necessárias para inserir os dados do Power BI em planilhas do Excel.

- Um modelador de dados do Power BI [promove ou certifica um conjunto de dados no Power BI](../connect-data/service-datasets-promote.md).
- O modelador de dados [identifica as tabelas em destaque](service-create-excel-featured-tables.md) no conjunto de dados e salva esse conjunto de dados no serviço do Power BI.
- O restante da organização pode se conectar a essas tabelas em destaque no Excel para obter dados relevantes e atualizáveis. O Excel se refere a essas tabelas como *tipos de dados* e as lista na Galeria de Tipos de Dados.

> [!NOTE]
> No Excel, você também pode obter dados de qualquer conjunto de dados que possa ser acessado no Power BI. Na faixa de opções **Dados**, selecione **Obter Dados** > **Do Power BI (Microsoft)** .
> :::image type="content" source="media/service-excel-featured-tables/excel-get-data-power-bi.png" alt-text="Captura de tela da opção Obter Dados do Power BI na faixa de opções Dados.":::

## <a name="the-excel-data-types-gallery"></a>A Galeria de Tipos de Dados do Excel
As tabelas em destaque nos conjuntos de dados do Power BI são exibidas como *tipos de dados* na faixa de opções **Dados**, na galeria de **Tipos de Dados** do Excel.

:::image type="content" source="media/service-excel-featured-tables/excel-data-ribbon.png" alt-text="Captura de tela da galeria de Tipos de Dados na faixa de opções Dados do Excel.":::

Quando expandida, a galeria mostra os tipos de dados genéricos, como **Ações** e **Geografia**, além dos dez principais tipos de dados da **Organização** disponíveis para você: as tabelas em destaque dos conjuntos de dados do Power BI.

:::image type="content" source="media/service-excel-featured-tables/excel-data-types-gallery.png" alt-text="Captura de tela da Galeria de Tipos de Dados do Excel.":::

## <a name="format-a-range-of-cells-as-a-table-optional"></a>Formatar um intervalo de células como uma tabela (opcional)

 Antes de você começar, recomendamos formatar seus dados como uma tabela do Excel. Dessa forma, as alterações feitas em uma linha serão aplicadas às outras linhas da tabela. 

1. Adicione um cabeçalho de coluna. 
2. Em seguida, selecione uma célula nos dados e clique em CTRL + T. 
3. Marque **Minha tabela tem cabeçalhos** > **OK**.

    :::image type="content" source="media/service-excel-featured-tables/excel-format-table.png" alt-text="Captura de tela da conversão de intervalo em tabela.":::

## <a name="search-for-power-bi-data-in-the-excel-data-types-gallery"></a>Pesquisar dados do Power BI na Galeria de Tipos de Dados do Excel

Para pesquisar dados em uma tabela em destaque do Power BI, selecione uma célula ou um intervalo na planilha do Excel que contém um valor que corresponda ao valor de uma tabela em destaque. Selecione **Organização**. O Excel pesquisará todas as tabelas em destaque às quais você tem acesso, procurando uma correspondência.

:::image type="content" source="media/service-excel-featured-tables/excel-table-organization.png" alt-text="Captura de tela de Selecionar uma célula ou um intervalo de células.":::
 
Se você souber a tabela em destaque que está procurando, escolha **Da sua organização (versão prévia)** na galeria e selecione-a.

:::image type="content" source="media/service-excel-featured-tables/excel-organizational-data-table.png" alt-text="Captura de tela de Dados Organizacionais do Excel, tabela de tipo de dados Fornecedores.":::
 
Quando você faz a pesquisa, se o Excel encontra linhas correspondentes com alta confiança, as células são imediatamente vinculadas a essas linhas. O ícone do item vinculado indica que as células estão vinculadas às linhas no Power BI.

:::image type="content" source="media/service-excel-featured-tables/excel-linked-card-icon.png" alt-text="Captura de tela do ícone do Item vinculado.":::

Se uma célula tiver mais de uma linha correspondente em potencial, a célula mostrará um ícone de ponto de interrogação e o painel do **Seletor de Dados** será aberto. No exemplo a seguir, o usuário selecionou um intervalo B2:B10 e procurou uma tabela em destaque do Power BI. Todas as linhas tinham correspondências, exceto a célula B5, "Ma Maison". O **Seletor de Dados** mostra duas correspondências possíveis.

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-pane.png" alt-text="Captura de tela do painel Seletor de Dados do Excel.":::
 
A opção Dados organizacionais pode retornar linhas de várias tabelas em destaque. O Excel agrupa as linhas potencialmente correspondentes pelo tipo de dados do qual elas vieram. O Excel classifica os tipos de dados com base na linha correspondente mais forte possível. Use as setas de divisa para recolher e expandir os tipos de dados para linhas correspondentes.

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-multiple.png" alt-text="Captura de tela do painel Seletor de Dados do Excel com várias possibilidades.":::
 
Para escolher a linha correta, selecione o nome da linha para ver mais detalhes. Depois de encontrá-la, clique em **Selecionar** para vincular a linha à célula no Excel. 

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-details.png" alt-text="Captura de tela dos detalhes do Seletor de Dados.":::
 
A seleção do ícone de **Cartão** na célula mostra um cartão com os dados de qualquer campo e os campos calculados na tabela em destaque. O título do cartão mostra o valor do campo do rótulo de linha na tabela em destaque.
 
:::image type="content" source="media/service-excel-featured-tables/excel-linked-item-details.png" alt-text="Captura de tela dos detalhes do Item vinculado.":::

Selecione o ícone **Inserir Dados** e escolha um nome de campo na lista de campos para adicionar o respectivo valor à grade.  

:::image type="content" source="media/service-excel-featured-tables/excel-select-field.png" alt-text="Captura de tela de Selecionar um nome de campo.":::

Os valores do campo são colocados nas células adjacentes. A fórmula da célula refere-se à célula vinculada e ao nome do campo, para que você possa usar os dados em funções do Excel.

:::image type="content" source="media/service-excel-featured-tables/excel-cell-formula.png" alt-text="Captura de tela da fórmula de célula do Excel.":::

## <a name="cell-formulas"></a>Fórmulas de células

Ao usar uma tabela do Excel, você pode fazer referência à coluna da tabela vinculada e, em seguida, adicionar campos de dados usando a referência de `.` (ponto).

:::image type="content" source="media/service-excel-featured-tables/excel-dot-reference.png" alt-text="Captura de tela da referência de período do Excel.":::

Da mesma forma, ao usar uma célula, você pode fazer referência à célula e usar a referência de `.` (ponto) para recuperar campos.

:::image type="content" source="media/service-excel-featured-tables/excel-cell-dot-reference.png" alt-text="Captura de tela da referência do período da célula.":::
 
## <a name="data-caching-and-refresh"></a>Atualização e cache de dados

Quando o Excel vincula uma célula a uma linha em uma tabela em destaque do Power BI, ele recupera e salva todos os valores do campo no arquivo do Excel. Qualquer pessoa com a qual você compartilha o arquivo pode fazer referência a qualquer um dos campos, sem solicitar dados do Power BI.  

Use o botão **Atualizar Tudo** na faixa de opções **Dados** para atualizar dados em células vinculadas. 

:::image type="content" source="media/service-excel-featured-tables/excel-refresh-all.png" alt-text="Captura de tela de Atualizar Tudo.":::
 
Você também pode atualizar células individuais. Clique com o botão direito do mouse na célula e selecione **Tipos de Dados** > **Atualizar**.

## <a name="show-a-card-change-or-convert-to-text"></a>Mostrar um cartão, alterar ou converter em texto

As células vinculadas têm opções de menu com o botão direito do mouse adicionadas. Clique com o botão direito do mouse em uma célula. Juntamente com as opções usuais, você também vê:

- **Mostrar Cartão do Tipo de Dados**.
- **Atualizar**.
- **Alterar**.
- **Converter em Texto**.

:::image type="content" source="media/service-excel-featured-tables/excel-right-click-data-type.png" alt-text="Captura de tela do clique com o botão direito do mouse, Converter em Texto.":::
 
**Converter em Texto** remove o link para a linha na tabela em destaque do Power BI. Além disso, o texto na célula será o valor do rótulo de linha da célula vinculada. Se você vinculou uma célula a uma linha que não pretendia, selecione **Desfazer** no Excel para restaurar os valores iniciais da célula.

## <a name="licensing"></a>Licenças

A galeria Tipos de Dados do Excel e experiências conectadas para tabelas em destaque do Power BI estão disponíveis somente para clientes do Excel E5 e G5. 

## <a name="security"></a>Segurança

Você vê somente tabelas em destaque de conjuntos de dados dos quais tem permissão no Power BI. Durante a atualização de dados, você deve ter permissão para acessar o conjunto de dados no Power BI para recuperar as linhas. Isso requer a permissão Criar ou Gravar no conjunto de dados. O Excel armazena em cache os dados retornados para a linha inteira. Qualquer pessoa com a qual você compartilha o arquivo do Excel pode ver os dados de todos os campos em todas as células vinculadas.

Se um conjunto de dados Power BI tiver segurança em nível de linha ou um rótulo de confidencialidade da Proteção de Informações da Microsoft aplicado a ele, as tabelas em destaque desse conjunto não serão incluídas na galeria Tipos de Dados do Excel. Essa é uma limitação da versão preliminar inicial.

## <a name="administrative-control"></a>Controle administrativo

Os administradores do Power BI podem controlar quem na organização pode usar tabelas em destaque na galeria Tipos de Dados do Excel. Confira [Configurações de tabelas em destaque](../admin/service-admin-portal.md#featured-tables-settings) no artigo do Portal de administração para obter detalhes. 
 
### <a name="auditing"></a>Auditoria

Os logs de auditoria de administração mostram estes eventos para tabelas em destaque:

- **AnalyzedByExternalApplication**: dá aos administradores visibilidade dos usuários que estão acessando cada tabela em destaque.
- **UpdateFeaturedTables**: dá aos administradores visibilidade dos usuários que estão publicando e atualizando tabelas em destaque.

Para obter uma lista completa dos eventos de log de auditoria, confira [Acompanhar atividades do usuário no Power BI](../admin/service-admin-auditing.md).

## <a name="considerations-and-limitations"></a>Considerações e limitações

Aqui estão as limitações para a versão preliminar inicial:

- A integração está disponível em compilações internas do Excel.
- A galeria Tipos de Dados do Excel inclui tabelas em destaque para usuários com a licença apropriada no Power BI Desktop e no serviço do Power BI. O suporte para o serviço do Power BI pode não estar disponível no lançamento da versão preliminar, mas será adicionado.
- As tabelas em destaque em conjuntos de dados do Power BI que usam os seguintes recursos não são mostradas no Excel: 

    - Conjuntos de dados de segurança em nível de linha.
    - Conjuntos de dados habilitados da Proteção de Informações da Microsoft.
    - Conjuntos de dados do DirectQuery.
    - Conjuntos de dados com uma conexão dinâmica.

- O Excel mostra somente os dados em colunas e colunas calculadas na tabela em destaque. Os itens a seguir não são fornecidos na versão preliminar inicial:

    - Medidas definidas na tabela de recursos.
    - Medidas definidas em tabelas relacionadas e medidas implícitas calculadas de relações.

- O Excel só exibe as tabelas em destaque (*tipos de dados*) armazenadas nos novos workspaces do Power BI. Tabelas em destaque armazenadas nos workspaces clássicos, ou em Meu Workspace, não são mostradas como tipos de dados no Excel. Você pode [atualizar workspaces clássicos para os novos workspaces](service-upgrade-workspaces.md) no Power BI.

A experiência de Tipos de Dados no Excel é semelhante a uma função de pesquisa. Usa um valor de célula fornecido pela planilha do Excel e pesquisa linhas correspondentes nas tabelas em destaque do Power BI. A experiência de pesquisa tem os seguintes comportamentos:

- Ao usar o botão **Dados Organizacionais** para pesquisar, o Excel pesquisa somente tabelas em destaque em conjuntos de dados certificados.
- A correspondência de linha é baseada em colunas de texto na tabela em destaque. Usa a mesma indexação que o recurso P e R do Power BI, que é otimizado para pesquisa em inglês. Pesquisar em outros idiomas pode não resultar em correspondências precisas. As colunas numéricas não são consideradas para correspondência.
- A correspondência é baseada em correspondências exatas e de prefixo para termos de pesquisa individuais. O valor de uma célula é dividido com base em espaços ou em outros caracteres de espaço em branco como guias. Em seguida, cada palavra é considerada um termo de pesquisa. Os valores do campo de texto de uma linha são comparados a cada termo de pesquisa para correspondências exatas e de prefixo. Uma correspondência de prefixo será retornada se o campo de texto da linha começar com o termo de pesquisa. Por exemplo, se uma célula contiver "São Paulo", então "São" e "Paulo" serão termos de pesquisa distintos. 

    - As linhas com colunas de texto cujo valor corresponda exatamente a "São" ou "Paulo" serão retornadas. 
    - As linhas com colunas de texto cujo valor comece com "São" ou "Paulo" serão retornadas. 
    - Além disso, as linhas que contenham "São" ou "Paulo", mas não comecem com esses valores, não serão retornadas.

- O Power BI retorna no máximo 100 sugestões de linha para cada célula.
- Não há suporte para a configuração ou atualização da tabela em destaque no ponto de extremidade XMLA
- Arquivos do Excel com um modelo de dados podem ser usados para publicar tabelas em destaque. Carregue os dados no Power BI Desktop e, em seguida, publique a tabela em destaque.
- Alterar o nome da tabela, o rótulo da linha ou a coluna de chave da tabela em destaque pode afetar os usuários do Excel com células vinculadas a linhas na tabela. 
- O Excel mostra quando os dados foram recuperados do conjunto de dados do Power BI. Isso não é necessariamente o momento em que os dados foram atualizados no Power BI, ou a hora do ponto de dados mais recente em um conjunto de dados. Por exemplo, digamos que um conjunto de dados no Power BI tenha sido atualizado há uma semana, mas os dados de origem subjacentes tinham uma semana quando a atualização ocorreu. Os dados reais seriam de duas semanas, mas o Excel mostraria os dados recuperados como a data/hora em que os dados foram obtidos no Excel.

## <a name="next-steps"></a>Próximas etapas

- [Definir tabelas em destaque no Power BI Desktop](service-create-excel-featured-tables.md)
- Leia mais sobre como [usar tipos de dados do Excel por meio do Power BI](https://support.office.com/article/use-excel-data-types-from-power-bi-preview-cd8938ce-f963-444d-b82a-7140848241e9) na documentação do Excel.
- Dúvidas? [Experimente a Comunidade do Power BI](https://community.powerbi.com/)

