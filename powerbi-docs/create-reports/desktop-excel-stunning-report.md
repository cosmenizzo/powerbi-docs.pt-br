---
title: 'Tutorial: Da pasta de trabalho do Excel para um relatório incrível no Power BI Desktop'
description: Este tutorial mostra como você pode criar rapidamente um relatório incrível com base em uma pasta de trabalho do Excel.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 07/21/2020
ms.author: maggies
LocalizationGroup: Data from files
ms.openlocfilehash: b628502ad5658388065a197c1c722a59dd9ad2b4
ms.sourcegitcommit: e9cd61eaa66eda01cc159251d7936a455c55bd84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "86972658"
---
# <a name="tutorial-from-excel-workbook-to-stunning-report-in-power-bi-desktop"></a>Tutorial: Da pasta de trabalho do Excel para um relatório incrível no Power BI Desktop

Neste tutorial, você criará um lindo relatório do início ao fim em 20 minutos. 

Sua gerente deseja ver um relatório sobre seus últimos números de vendas. Ela solicitou um resumo executivo de: 

- Qual mês e ano tiveram mais lucro? 
- Onde a empresa está tendo mais sucesso (por país)? 
- Em qual produto e segmento a empresa deve continuar investindo? 

Usando nossa pasta de trabalho de finanças de exemplo, podemos criar esse relatório em poucos instantes. Esta será aparência do relatório final. Vamos começar! 

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-excel-formatted-report.png" alt-text="Captura de tela do relatório do Power BI no serviço do Power BI."::: 

Neste tutorial, você aprenderá a:

> [!div class="checklist"]
> * Baixar os dados de exemplo
> * Preparar seus dados com algumas transformações
> * Criar um relatório com um título, três visuais e uma segmentação
> * Publicar seu relatório no serviço do Power BI para compartilhá-lo com seus colegas

## <a name="prerequisites"></a>Pré-requisitos

- Antes de começar, você precisará [baixar o Power BI Desktop](https://powerbi.microsoft.com/desktop/).
- Se estiver planejando publicar seu relatório no serviço do Power BI e ainda não estiver inscrito, [inscreva-se em uma avaliação gratuita](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="download-the-sample"></a>Baixe o exemplo

Para acompanhar o tutorial, baixe a pasta de trabalho de exemplo. 

1. Baixe a [pasta de trabalho Exemplo financeiro do Excel](https://go.microsoft.com/fwlink/?LinkID=521962).
1. Abra o Power BI Desktop.
1. Na seção **Dados** da faixa de opções **Página Inicial**, selecione **Excel**.
1. Acesse o local em que você salvou a pasta de trabalho de exemplo e selecione **Abrir**.

## <a name="prepare-your-data"></a>Preparar seus dados 

No **Navegador**, você tem a opção de *transformar* ou *carregar* os dados. O Navegador fornece uma visualização dos dados para que você possa verificar se tem o intervalo de dados correto. Os tipos de dados numéricos são exibidos em itálico. Caso precise fazer alterações, transforme seus dados antes de carregá-los. Para facilitar a leitura das visualizações mais tarde, queremos transformar os dados agora. Ao fazer cada transformação, você a verá adicionada à lista em **Configurações de Consulta** em **Etapas Aplicadas** 

1. Selecione a tabela **Finanças** e escolha **Transformar Dados**. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-financial-navigator.png" alt-text="Captura de tela do Navegador do Power BI com os dados do Exemplo financeiro."::: 

1. Selecione a coluna **Unidades Vendidas**. Na guia **Página Inicial**, selecione **Tipo de Dados** e **Número Inteiro**. Escolha **Substituir atual** para alterar o tipo de coluna. 

    A principal etapa de limpeza de dados que os usuários costumam fazer é alterar os tipos de dados. Nesse caso, as unidades vendidas estão no formato decimal. Não faz sentido ter 0,2 ou 0,5 de uma unidade vendida, faz? Então, vamos alterar isso para um número inteiro. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-query-whole-number.png" alt-text="Captura de tela da alteração de um número decimal para um número inteiro."::: 

1. Selecione a coluna **Segmento**. Na guia **Transformar**, selecione **Formato** e **LETRAS MAIÚSCULAS**.

    Também queremos facilitar a visualização dos segmentos no gráfico posteriormente. Vamos formatar a coluna Segmento. 

     :::image type="content" source="media/desktop-excel-stunning-report/power-query-upper-case.png" alt-text="captura de tela da alteração de títulos de letras minúsculas para maiúsculas.":::

1. Vamos abreviar o nome da coluna de **Nome do Mês** para apenas **Mês**. Clique duas vezes na coluna **Nome do Mês** e renomeie-a para apenas **Mês**.  

     :::image type="content" source="media/desktop-excel-stunning-report/power-query-month-name.png" alt-text="Captura de tela da abreviação do nome da coluna.":::

1. Na coluna **Produto**, selecione o menu suspenso e desmarque a caixa ao lado de **Montana**. 

     Sabemos que o produto Montana foi descontinuado no mês passado e, portanto, queremos filtrar esses dados do relatório para evitar confusão. 

     :::image type="content" source="media/desktop-excel-stunning-report/power-query-montana.png" alt-text="Captura de tela da exclusão de valores de Montana.":::

1. Você verá que cada transformação foi adicionada à lista em **Configurações de Consulta** em **Etapas Aplicadas**.

    :::image type="content" source="media/desktop-excel-stunning-report/power-query-applied-steps.png" alt-text="Captura de tela da lista de etapas aplicadas.":::

1. De volta à guia **Página Inicial**, selecione **Fechar e Aplicar**. Nossos dados estão quase prontos para a criação de um relatório. 

    Você consegue ver o símbolo de Sigma na lista Campos? O Power BI detectou que esses campos são numéricos. O Power BI também indica o campo de data com um símbolo de calendário.

     :::image type="content" source="media/desktop-excel-stunning-report/power-bi-fields-list-sigmas-date.png" alt-text="Captura de tela da lista Campos com os campos numéricos e o campo de data.":::

### <a name="extra-credit-write-a-measure-in-dax"></a>Crédito extra: Escrever uma medida em DAX

Escrever *medidas* na linguagem de fórmula *DAX* é excelente para a modelagem de dados. Há muito a aprender sobre o DAX na documentação do Power BI. Por enquanto, vamos escrever uma medida básica e unir duas tabelas. 

1. Selecione **Exibição de Dados** à esquerda. 
 
    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-data-view.png" alt-text="Captura de tela do ícone de Exibição de Dados.":::

1. Na faixa de opções **Página Inicial**, selecione **Nova Tabela**. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-new-table.png" alt-text="Captura de tela do ícone de Nova Tabela.":::

1. Digite essa medida para gerar uma tabela Calendário de todas as datas entre 1º de janeiro de 2013 e 31 de dezembro de 2014.  

    `Calendar = CALENDAR(DATE(2013,01,01),Date(2014,12,31))` 

2. Selecione a marca de seleção para fazer a confirmação.

     :::image type="content" source="media/desktop-excel-stunning-report/power-bi-dax-expression.png" alt-text="Captura de tela da expressão DAX.":::

1. Agora, selecione **Exibição de Modelo** à esquerda. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-model-view.png" alt-text="Captura de tela do ícone de Exibição de Modelo.":::

1. Arraste o campo **Data** da tabela Finanças para o campo **Data** na tabela Calendário para unir as tabelas e crie uma *relação* entre elas.  

     :::image type="content" source="media/desktop-excel-stunning-report/power-bi-date-relationship.png" alt-text="Captura de tela de relação entre os campos de Data.":::

## <a name="build-your-report"></a>Criar seu relatório 

Agora que você transformou e carregou seus dados, é hora de criar o relatório. No painel Campos à direita, você vê os campos no modelo de dados criado. 

Vamos criar o relatório final, um visual por vez. 

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-report-by-numbers.png" alt-text="Captura de tela de todos os elementos do relatório, por número.":::

### <a name="visual-1-add-a-title"></a>Visual 1: Adicionar um título 

1. Na faixa de opções **Inserir**, selecione **Caixa de Texto**. Digite “Resumo Executivo – Relatório de Finanças”. 
1. Selecione o texto que você digitou. Defina o tamanho da fonte como 20 e negrito. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-title-executive-summary.png" alt-text="Captura de tela da formatação do título.":::

1. No painel Visualizações, alterne a **Tela de Fundo** para **Desativada**. 
1. Redimensione a caixa para que ela se ajuste em uma linha. 

### <a name="visual-2-profit-by-date"></a>Visual 2: Lucro por Data 

Agora, você criará um gráfico de linhas para ver qual mês e ano tiveram o lucro mais alto. 

1. No painel Campos, arraste o campo **Lucro** para uma área em branco na tela do relatório. Por padrão, o Power BI exibe um gráfico de colunas com uma coluna, Lucro. 
1. Arraste o campo **Data** para o mesmo visual. O Power BI atualizará o gráfico de colunas para mostrar o lucro pelos dois anos.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-column-year.png" alt-text="Captura de tela do gráfico de colunas Lucro.":::

1. Na seção **Campos** do painel Visualizações, selecione o menu suspenso no valor **Eixo**. Altere **Data** de **Hierarquia de Data** para **Data**.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-date-hierarchy.png" alt-text="Captura de tela da alteração da Hierarquia de data para Data.":::

    O Power BI atualizará o gráfico de colunas para mostrar o lucro de cada mês.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-column-month.png" alt-text="Captura de tela do gráfico de colunas por mês.":::

1. No painel Visualizações, altere o tipo de visualização para **Gráfico de linhas**. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-profit-date-line-chart.png" alt-text="Captura da coluna da alteração do gráfico de colunas para o gráfico de barras.":::

    Agora você pode ver com facilidade que o mês de dezembro de 2014 teve o maior lucro.

### <a name="visual-3-profit-by-country"></a>Visual 3: Lucro por País 

Crie um mapa para ver qual país teve os maiores lucros.

1. No painel Campos, arraste o campo **País** para uma área em branco na tela do relatório para criar um mapa.
1. Arraste o campo **Lucro** para o mapa.

    O Power BI cria um visual de mapa com bolhas que representam o lucro relativo de cada local. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-map-visual.png" alt-text="Captura de tela da criação do gráfico de mapa.":::

    A Europa parece estar tendo um desempenho melhor do que a América do Norte. 

### <a name="visual-4-sales-by-product-and-segment"></a>Visual 4: Vendas por Produto e Segmento 

Crie um gráfico de barras para determinar em quais empresas e segmentos a empresa deve investir.

1. Arraste os dois gráficos que você criou para ficarem lado a lado na metade superior da tela. Economize espaço no lado esquerdo da tela. 
1. Selecione uma área em branco na metade inferior da tela do relatório. 

1. No painel Campos, selecione os campos **Vendas**, **Produto** e **Segmento**. 

    O Power BI criará automaticamente um gráfico de colunas clusterizado. 

1. Arraste o gráfico, de modo que ele fique grande o suficiente para preencher o espaço abaixo dos dois gráficos superiores.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-clustered-column-chart.png" alt-text="Captura de tela de um gráfico de colunas clusterizado.":::

    Parece que a empresa deve continuar investindo no produto Paseo e ter como alvo os segmentos Pequenas Empresas e Governo.  

### <a name="visual-5-year-slicer"></a>Visual 5: Segmentação de ano 

As segmentações são uma ferramenta útil para filtrar os visuais em uma página de relatório para uma seleção específica. Nesse caso, podemos criar uma segmentação para restringir o desempenho de cada mês e ano.  

1. No painel Campos, selecione o campo **Data** e arraste-o para a área em branco à esquerda da tela. 
2. No painel Visualizações, escolha **Segmentação**. 
3. Na seção Campos do painel Visualizações, selecione o menu suspenso em **Campos**. Remova Trimestre e Dia para que apenas Ano e Mês sejam mantidos. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-date-hierarchy-trim.png" alt-text="Captura de tela da alteração da Hierarquia de data.":::

4. Expanda todos os anos e redimensione o visual, de modo que todos os meses fiquem visíveis.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-hierarchy-date-slicer.png" alt-text="Captura de tela da segmentação da hierarquia de data.":::

Agora, se a sua gerente solicitar apenas os dados de 2013, você poderá usar a segmentação para alternar entre anos ou meses específicos de cada ano. 

### <a name="extra-credit-format-the-report"></a>Crédito extra: Formatar o relatório

Se você quiser uma formatação leve nesse relatório para aperfeiçoá-lo, veja a seguir algumas etapas fáceis. 

**Tema**

- Na faixa de opções **Exibição**, altere o tema para **Executivo**.  

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-theme-executive.png" alt-text="Captura de tela de seleção do tema Executivo."::: 

**Sofisticar os visuais** 

Faça as alterações a seguir na guia **Formatar** no painel Visualizações.

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-format-tab-visualizations.png" alt-text="Captura de tela da guia Formato no painel Visualizações.":::

1. Selecione Visual 2. Na seção **Título**, altere o **Texto do título** para “Lucro por Mês e Ano” e o **Tamanho do texto** para **16 pt**. Alterne **Sombra** para **Ativado**. 

1. Selecione Visual 3. Na seção **Estilos de mapa**, altere **Tema** para **Escala de cinza**. Na seção **Título**, altere o **Tamanho do texto** do título para **16 pt**. Alterne **Sombra** para **Ativado**.

1. Selecione Visual 4. Na seção **Título**, altere o **Tamanho do texto** do título para **16 pt**. Alterne **Sombra** para **Ativado**.

1. Selecione Visual 5. Na seção **Controles de seleção**, alterne **Mostrar a opção "Selecionar tudo"** para **Ativado**. Na seção **Cabeçalho de segmentação**, aumente o **Tamanho do texto** para **16 pt**. 

**Adicionar uma forma da tela de fundo para o título**

1. Na faixa de opções **Inserir**, selecione **Formas** > **Retângulo**. Coloque-o na parte superior da página e alongue-o para que ele tenha a largura da página e a altura do título. 
1. No painel **Formatar forma**, na seção **Linha**, altere **Transparência** para **100%** . 
1. Na seção **Preenchimento**, altere **Cor de preenchimento** para **Cor do tema 5 #6B91C9** (azul). 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-theme-color-5.png" alt-text="Captura de tela da Cor do tema 5.":::

1. Na guia **Formatar**, selecione **Recuar** > **Enviar para trás**. 
1. Selecione o texto no Visual 1 e o título e altere a cor da fonte para **Branco**. 

**Adicionar uma forma da tela de fundo para os visuais 2 e 3**

1. Na faixa de opções **Inserir**, selecione **Formas** > **Retângulo** e alongue-o para que ele tenha a largura e a altura dos visuais 2 e 3. 
1. No painel **Formatar forma**, na seção **Linha**, altere **Transparência** para **100%** . 
1. Na guia **Formatar**, selecione **Recuar** > **Enviar para trás**. 

### <a name="finished-report"></a>Relatório concluído

Veja como ficará seu relatório final aperfeiçoado:  

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-excel-formatted-report.png" alt-text="Captura de tela do relatório final formatado.":::

Em resumo, este relatório responde às principais perguntas da sua gerente: 

- Qual mês e ano tiveram mais lucro? 

    Dezembro de 2014 

- Em qual país a empresa está tendo mais sucesso? 

    Na Europa, especificamente, na França e na Alemanha. 

- Em qual produto e segmento a empresa deve continuar investindo? 

    A empresa deve continuar investindo no produto Paseo e ter como alvo os segmentos Pequenas Empresas e Governo. 

## <a name="save-your-report"></a>Salvar seu relatório

- No menu **Arquivo**, selecione **Salvar**.

## <a name="publish-to-the-power-bi-service-to-share"></a>Publicação no serviço do Power BI para compartilhamento 

Para compartilhar seu relatório com a sua gerente e seus colegas, publique-o no serviço do Power BI. Quando você o compartilha com os colegas que têm uma conta do Power BI, eles podem interagir com o relatório, mas não podem salvar as alterações. 

1. No Power BI Desktop, selecione **Publicar** na faixa de opções **Página Inicial**. 

    Talvez você precise entrar no serviço do Power BI. Se não tiver uma conta do Azure, [inscreva-se em uma avaliação gratuita](https://app.powerbi.com/signupredirect?pbi_source=web).

1. Selecione um destino, como **Meu workspace** no serviço do Power BI > **Selecionar**.
1. Escolha **Abrir 'nome-do-arquivo' no Power BI**.

    :::image type="content" source="media/desktop-excel-stunning-report/open-power-bi.png" alt-text="Captura de tela da abertura do relatório no serviço do Power BI.":::

    O relatório concluído será aberto no navegador.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-excel-report-service.png" alt-text="Captura de tela do relatório do Power BI no serviço do Power BI."::: 

1. Selecione **Compartilhar** na parte superior do relatório para compartilhar seu relatório com outras pessoas.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-share-report.png" alt-text="Captura de tela de compartilhamento do relatório por meio do serviço do Power BI.":::

## <a name="next-steps"></a>Próximas etapas

- [Tutorial: Analisar dados de vendas no Excel e um feed OData](../connect-data/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed.md)

Mais perguntas? [Experimente a Comunidade do Power BI](https://community.powerbi.com/).
