---
title: Acessar tabelas em destaque do Power BI no Excel (versão preliminar)
description: No Excel, você pode encontrar dados de tabelas em destaque em conjuntos de dados do Power BI na Galeria de Tipos de Dados.
author: maggiesMSFT
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 08/04/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 099e3aa11662232c5362895e93f0433620ce2ba9
ms.sourcegitcommit: a7227f6d3236e6e0a7bc1f83ff6099b5cd58bff3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87768827"
---
# <a name="access-power-bi-featured-tables-in-excel-preview"></a>Acessar tabelas em destaque do Power BI no Excel (versão preliminar)

As *tabelas em destaque* são uma forma de vincular seus dados no Excel aos dados no Power BI. Elas facilitam a adição de dados empresariais às suas planilhas do Excel. Na Galeria de Tipos de Dados do Excel, você encontra dados das tabelas em destaque em conjuntos de dados do Power BI. Este artigo explica como fazer isso.

Você cria conjuntos de dados no Power BI? Leia sobre a [configuração de tabelas em destaque no Power BI Desktop](service-create-excel-featured-tables.md).

> [!NOTE]
> No Excel, você também pode analisar dados de qualquer conjunto de dados do Power BI que possa ser acessado no Power BI. Confira [Outras maneiras de acessar conjuntos de dados do Power BI desde o Excel](service-analyze-in-excel.md#other-ways-to-access-power-bi-datasets-from-excel) no artigo "Analisar no Excel para o Power BI" para obter detalhes.
> 

## <a name="the-excel-data-types-gallery"></a>A Galeria de Tipos de Dados do Excel
As tabelas em destaque nos conjuntos de dados do Power BI são exibidas como *tipos de dados* na faixa de opções **Dados**, na galeria de **Tipos de Dados** do Excel.

:::image type="content" source="media/service-excel-featured-tables/excel-data-ribbon.png" alt-text="Captura de tela da galeria de Tipos de Dados na faixa de opções Dados do Excel.":::

Quando expandida, a galeria mostra os tipos de dados genéricos, como **Ações** e **Geografia**, além dos dez principais tipos de dados da **Organização** disponíveis para você: as tabelas em destaque dos conjuntos de dados do Power BI.

:::image type="content" source="media/service-excel-featured-tables/excel-data-types-gallery.png" alt-text="Captura de tela da Galeria de Tipos de Dados do Excel.":::

## <a name="search-for-power-bi-data-in-the-data-types-gallery"></a>Pesquisar dados do Power BI na Galeria de Tipos de Dados

Para pesquisar dados em uma tabela em destaque do Power BI, selecione uma célula ou um intervalo na planilha do Excel que contém um valor que corresponda ao valor de uma tabela em destaque. Selecione a seta **Mais** ao lado da galeria de Tipos de Dados.

:::image type="content" source="media/service-excel-featured-tables/excel-data-types-more.png" alt-text="Captura de tela do ícone Mais na galeria de Tipos de Dados do Excel.":::

Se você vir a tabela que está procurando, selecione-a. Caso contrário, selecione **Mais de sua organização**. O Excel pesquisará todas as tabelas em destaque às quais você tem acesso, procurando uma correspondência.

:::image type="content" source="media/service-excel-featured-tables/excel-more-your-organization.png" alt-text="Captura de tela da seleção da opção De sua organização (versão prévia).":::
 
O Excel exibe todas as tabelas possíveis. No painel **Seletor de Dados**, digite a caixa **Filtro** para restringir suas opções. Selecione a tabela correspondente.

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-store.png" alt-text="Captura de tela de Dados Organizacionais do Excel, tabela de tipo de dados Fornecedores.":::
 
Se o Excel encontrar linhas correspondentes com alta confiança, as células serão imediatamente vinculadas a essas linhas. O ícone do item vinculado indica que as células estão vinculadas às linhas no Power BI.

:::image type="content" source="media/service-excel-featured-tables/excel-linked-card-icon.png" alt-text="Captura de tela do ícone do Item vinculado.":::

Se uma célula tiver mais de uma linha correspondente em potencial, a célula mostrará um ícone de ponto de interrogação e o painel do **Seletor de Dados** será aberto. No exemplo a seguir, selecionamos um intervalo B3:B9 e selecionamos a tabela em destaque do Power BI chamada **Store**. Todas as linhas tinham correspondências, exceto a célula B9, "508 – Pasadena Lindseys". O **Seletor de Dados** mostra duas correspondências possíveis, o mesmo valor em duas tabelas diferentes.

:::image type="content" source="media/service-excel-featured-tables/excel-question-mark-featured-table.png" alt-text="Captura de tela do painel Seletor de Dados do Excel.":::
 
A opção Dados organizacionais pode retornar linhas de várias tabelas em destaque. O Excel agrupa as linhas potencialmente correspondentes pelo tipo de dados do qual elas vieram. O Excel classifica os tipos de dados com base na linha correspondente mais forte possível. Use as setas de divisa para recolher e expandir os tipos de dados para linhas correspondentes.

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-multiple.png" alt-text="Captura de tela do painel Seletor de Dados do Excel com várias possibilidades.":::
 
Para cada sugestão, selecione o nome da linha no painel **Seletor de Dados** para ver mais detalhes na linha, ajudando-o a escolher a linha correta. Depois de encontrá-la, clique em **Selecionar** para vincular a linha à célula no Excel. 

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-details.png" alt-text="Captura de tela dos detalhes do Seletor de Dados.":::

## <a name="explore-related-data"></a>Explorar dados relacionados

Agora que você criou a conexão entre os valores em sua planilha do Excel e os dados na tabela do Power BI em destaque, é possível explorar esses dados. Use os dados para aprimorar seus relatórios do Excel.

### <a name="view-related-data-in-a-card"></a>Exibir os dados relacionados em um cartão 
 
Selecione o ícone de **Cartão** na célula para mostrar um cartão com os dados de qualquer campo e os campos calculados na tabela em destaque. O título do cartão mostra o valor do campo do rótulo de linha na tabela em destaque.
 
:::image type="content" source="media/service-excel-featured-tables/excel-linked-item-details.png" alt-text="Captura de tela dos detalhes do Item vinculado.":::

### <a name="insert-related-data-from-power-bi"></a>Inserir dados relacionados do Power BI 

Selecione o ícone **Inserir Dados** e escolha um nome de campo na lista de campos para adicionar o respectivo valor à grade.  

:::image type="content" source="media/service-excel-featured-tables/excel-select-field.png" alt-text="Captura de tela de Selecionar um nome de campo.":::

Os valores do campo são colocados nas células adjacentes. A fórmula da célula refere-se à célula vinculada e ao nome do campo, para que você possa usar os dados em funções do Excel.

:::image type="content" source="media/service-excel-featured-tables/excel-cell-formula.png" alt-text="Captura de tela da fórmula de célula do Excel.":::

### <a name="use-cell-formulas"></a>Usar fórmulas de células

Em uma tabela do Excel, é possível fazer referência à coluna da tabela vinculada e, em seguida, adicionar campos de dados usando a referência de `.` (ponto).

:::image type="content" source="media/service-excel-featured-tables/excel-dot-reference.png" alt-text="Captura de tela da referência de período do Excel.":::

Da mesma forma, ao usar uma célula, é possível fazer referência à célula e usar a referência de `.` (ponto) para recuperar campos.

:::image type="content" source="media/service-excel-featured-tables/excel-cell-dot-reference.png" alt-text="Captura de tela da referência do período da célula.":::

### <a name="show-a-card-change-or-convert-to-text"></a>Mostrar um cartão, alterar ou converter em texto

As células vinculadas têm opções de menu com o botão direito do mouse adicionadas. Clique com o botão direito do mouse em uma célula. Juntamente com as opções usuais, você também vê:

- **Mostrar Cartão do Tipo de Dados**.
- **Tipo de Dados** > **Converter em Texto**.
- **Tipo de Dados** > **Alterar**.
- **Atualizar**.

:::image type="content" source="media/service-excel-featured-tables/excel-right-click-data-type.png" alt-text="Captura de tela do clique com o botão direito do mouse, Converter em Texto.":::
 
**Converter em Texto** remove o link para a linha na tabela em destaque do Power BI. Além disso, o texto na célula será o valor do rótulo de linha da célula vinculada. Se você vinculou uma célula a uma linha que não pretendia, selecione **Desfazer** no Excel para restaurar os valores iniciais da célula.
 
## <a name="data-caching-and-refresh"></a>Atualização e cache de dados

Quando o Excel vincula uma célula a uma linha em uma tabela em destaque do Power BI, ele recupera e salva todos os valores do campo no arquivo do Excel. Qualquer pessoa com a qual você compartilha o arquivo pode fazer referência a qualquer um dos campos, sem solicitar dados do Power BI.  

Use o botão **Atualizar Tudo** na faixa de opções **Dados** para atualizar dados em células vinculadas. 

:::image type="content" source="media/service-excel-featured-tables/excel-refresh-all.png" alt-text="Captura de tela de Atualizar Tudo.":::
 
Você também pode atualizar células individuais. Clique com o botão direito do mouse na célula e selecione **Tipos de Dados** > **Atualizar**.

## <a name="licensing"></a>Licenças

A galeria Tipos de Dados do Excel e experiências conectadas para tabelas em destaque do Power BI estão disponíveis somente para clientes do Excel E5 e G5. 

## <a name="security"></a>Segurança

Você vê somente tabelas em destaque de conjuntos de dados dos quais tem permissão no Power BI. Durante a atualização de dados, você deve ter permissão para acessar o conjunto de dados no Power BI para recuperar as linhas. Você precisa da [permissão Criar ou Gravar no conjunto de dados](../connect-data/service-datasets-build-permissions.md) no Power BI.
 
O Excel armazena em cache os dados retornados para a linha inteira. Qualquer pessoa com a qual você compartilha o arquivo do Excel pode ver os dados de todos os campos em todas as células vinculadas.

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

- Ao usar o botão **Dados Organizacionais** para pesquisar, o Excel pesquisa somente tabelas em destaque em conjuntos de dados do Power BI.
- A correspondência de linha é baseada em colunas de texto na tabela em destaque. Usa a mesma indexação que o recurso P e R do Power BI, que é otimizado para pesquisa em inglês. Pesquisar em outros idiomas pode não resultar em correspondências precisas. As colunas numéricas não são consideradas para correspondência.
- A correspondência é baseada em correspondências exatas e de prefixo para termos de pesquisa individuais. O valor de uma célula é dividido com base em espaços ou em outros caracteres de espaço em branco como guias. Em seguida, cada palavra é considerada um termo de pesquisa. Os valores do campo de texto de uma linha são comparados a cada termo de pesquisa para correspondências exatas e de prefixo. Uma correspondência de prefixo será retornada se o campo de texto da linha começar com o termo de pesquisa. Por exemplo, se uma célula contiver "São Paulo", então "São" e "Paulo" serão termos de pesquisa distintos. 

    - As linhas com colunas de texto cujos valores corresponderem exatamente a "São" ou "Paulo" serão retornadas. 
    - As linhas com colunas de texto cujos valores começarem a "São" ou "Paulo" serão retornadas. 
    - Além disso, as linhas que contenham "São" ou "Paulo", mas não comecem com esses valores, não serão retornadas.

- O Power BI retorna no máximo 100 sugestões de linha para cada célula.
- Não há suporte para a configuração ou atualização da tabela em destaque no ponto de extremidade XMLA
- Arquivos do Excel com um modelo de dados podem ser usados para publicar tabelas em destaque. Carregue os dados no Power BI Desktop e, em seguida, publique a tabela em destaque.
- Alterar o nome da tabela, o rótulo da linha ou a coluna de chave da tabela em destaque pode afetar os usuários do Excel com células vinculadas a linhas na tabela. 
- O Excel mostra quando os dados foram recuperados do conjunto de dados do Power BI. Essa hora não é necessariamente o momento em que os dados foram atualizados no Power BI, nem a hora do ponto de dados mais recente em um conjunto de dados. Por exemplo, digamos que um conjunto de dados no Power BI tenha sido atualizado há uma semana, mas os dados de origem subjacentes tinham uma semana quando a atualização ocorreu. Os dados reais seriam de duas semanas atrás, mas o Excel mostraria os dados recuperados como a data/hora em que os dados foram obtidos no Excel.

## <a name="next-steps"></a>Próximas etapas

- [Definir tabelas em destaque no Power BI Desktop](service-create-excel-featured-tables.md)
- Leia mais sobre como [usar tipos de dados do Excel por meio do Power BI](https://support.office.com/article/use-excel-data-types-from-power-bi-preview-cd8938ce-f963-444d-b82a-7140848241e9) na documentação do Excel.
- Dúvidas? [Experimente a Comunidade do Power BI](https://community.powerbi.com/)

