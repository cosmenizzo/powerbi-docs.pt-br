---
title: Inserir dados diretamente em um relatório paginado no Construtor de Relatórios
description: Neste artigo, você verá como inserir dados diretamente em um relatório paginado no Construtor de Relatórios.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: how-to
ms.date: 07/10/2020
ms.author: maggies
ms.openlocfilehash: f362303a79acb3468d6523eb24383ca0f3d49609
ms.sourcegitcommit: e8ed3d120699911b0f2e508dc20bd6a9b5f00580
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2020
ms.locfileid: "86264587"
---
# <a name="enter-data-directly-in-a-paginated-report-in-report-builder---power-bi"></a>Inserir dados diretamente em um relatório paginado no Construtor de Relatórios – Power BI

Neste artigo, você aprenderá mais sobre um recurso da nova versão do Microsoft Power BI Report Builder que permite inserir dados diretamente em um relatório de RDL como um conjunto de dados inserido.  Esse recurso é semelhante ao Power BI Desktop. Você pode digitar os dados diretamente em um conjunto de dados em seu relatório ou colá-los de outro programa, como o Microsoft Excel. Depois de criar um conjunto de dados inserindo dados, você pode usá-lo exatamente como faria com qualquer outro conjunto de dados inserido que você criou. Além disso, você pode adicionar mais de uma tabela e usá-la como um filtro para as outras. Esse recurso é especialmente útil para conjuntos de dados de pequenos e estáticos que talvez você precise usar em seu relatório, como parâmetros de relatório.
 
## <a name="prerequisites"></a>Pré-requisitos

- Para inserir dados diretamente em um relatório paginado, [baixe e instale o Power BI Report Builder](https://aka.ms/pbireportbuilder). 
- Para salvar seu relatório paginado no serviço do Power BI, você precisa de uma [conta do Power BI Pro](../fundamentals/service-self-service-signup-for-power-bi.md) e acesso de gravação a um workspace em uma [capacidade do Power BI Premium](../admin/service-premium-what-is.md).
- Para salvar seu relatório paginado em um servidor de relatório, você precisa de permissões para [editar o arquivo RsReportServer.config](#upload-the-paginated-report-to-a-report-server).

## <a name="create-a-data-source-and-dataset"></a>Criar uma fonte de dados e um conjunto de dados

Depois de baixar e instalar o Construtor de Relatórios, siga o mesmo fluxo de trabalho que você usa para adicionar uma fonte de dados inserida e o conjunto de dados ao seu relatório. No procedimento a seguir, em **Fontes de Dados**, há uma nova opção: **Inserir Dados**.  Você precisa configurar essa fonte de dados apenas uma vez em um relatório. Depois disso, você pode criar várias tabelas de dados inseridos como conjuntos de dados separados, tudo usando essa fonte de dados única.

1. No painel **Dados do Relatório**, selecione **Novo** > **Conjunto de Dados**.

    ![Captura de tela de Novo Conjunto de Dados do Report Builder.](media/paginated-reports-enter-data/paginated-new-dataset.png)

1. Na caixa de diálogo **Propriedades do Conjunto de Dados**, selecione **Usar um conjunto de dados inserido em meu relatório**.

1. Ao lado de **Fonte de dados**, selecione **Novo**.

    ![Captura de tela de Nova fonte de dados inserida.](media/paginated-reports-enter-data/paginated-new-data-source.png)

1. Na caixa de diálogo **Propriedades da Fonte de Dados**, selecione **Usar uma conexão inserida no meu relatório**.
2. Na caixa **Selecionar tipo de conexão**, selecione **INSERIR DADOS** > **OK**.

    ![Captura de tela da fonte de dados INSERIR DADOS.](media/paginated-reports-enter-data/paginated-data-source-properties-enter-data.png)

1. De volta à caixa de diálogo **Propriedades do Conjunto de Dados**, selecione **Designer de Consultas**.
2. No painel **Designer de Consulta**, clique com o botão direito do mouse e cole seus dados na tabela.

    ![Captura de tela de Inserir dados no Designer de Consultas.](media/paginated-reports-enter-data/paginated-enter-data.png)

1. Para definir os nomes de coluna, clique duas vezes em cada **NewColumn** e digite o nome da coluna.

    ![Captura de tela de Definir nomes de colunas.](media/paginated-reports-enter-data/paginated-column-name.png)

1. Se a primeira linha contiver cabeçalhos de coluna dos dados originais, clique com o botão direito do mouse nela e exclua-a.
    
9. Por padrão, o tipo de dados para cada coluna é a Cadeia de Caracteres. Para alterar o tipo de dados, clique com o botão direito do mouse no cabeçalho da coluna > **Alterar Tipo** e defina-o como outro tipo de dados, como Data ou Float.

    ![Captura de tela de Alterar tipo de dados.](media/paginated-reports-enter-data/paginated-data-type.png)

1. Quando você terminar de criar a tabela, selecione **OK**.  

    A consulta gerada é a mesmo que você veria com uma fonte de dados XML. Nos bastidores, estamos usando XML como o provedor de dados.  Podemos ter remodelado-o para habilitar esse cenário também.

    ![Captura de tela de Estrutura de dados XML.](media/paginated-reports-enter-data/paginated-xml-data.png)

12. Na caixa de diálogo **Propriedades do Conjunto de Dados**, selecione **OK**.

13. Você verá sua fonte de dados e o conjunto de dados no painel **Relatório de Dados**.

    ![Captura de tela do Conjunto de dados no painel Dados do Relatório.](media/paginated-reports-enter-data/paginated-report-data-pane.png)

Você pode usar o conjunto de dados como a base para visualizações de dados em seu relatório. Você também pode adicionar outro conjunto de dados e usar a mesma fonte de dados para ele.

## <a name="design-the-report"></a>Criar o relatório

Agora que tem uma fonte de dados e um conjunto de dados, você está pronto para criar seu relatório. O procedimento a seguir cria um relatório simples com base nos dados da seção anterior.

1. No menu **Inserir**, selecione **Tabela** > **Assistente de Tabela**.

    :::image type="content" source="media/paginated-reports-enter-data/paginated-table-wizard.png" alt-text="Captura de tela da seleção da opção Assistente de Tabela.":::

1. Selecione o conjunto de dados recém-criado > **Avançar**.

    :::image type="content" source="media/paginated-reports-enter-data/paginated-choose-dataset.png" alt-text="Captura de tela da caixa de diálogo Escolher um conjunto de dados.":::

2.  Na página Organizar campos, arraste os campos pelos quais deseja fazer o agrupamento da caixa **Campos disponíveis** para a caixa **Grupos de linhas**. Neste exemplo:

    - CountryRegion
    - SalesYear

3.  Arraste os campos que deseja agregar da caixa de **Campos disponíveis** para a caixa **Valores**. Neste exemplo:

    - SalesAmount

    Por padrão, o Report Builder soma os campos da caixa **Valores**, mas você pode escolher outra agregação.

    :::image type="content" source="media/paginated-reports-enter-data/paginated-select-aggregation.png" alt-text="Captura de tela de diferentes agregações para escolha.":::
 
1. Selecione **Avançar**.
4.  Na página **Escolher o layout**, mantenha todas as configurações padrão, mas desmarque **Expandir/recolher grupos**. Em geral, expandir e recolher grupos é ótimo, mas desta vez queremos ver todos os dados.

5.  Selecione **Avançar** > **Concluir**. A tabela é exibida na superfície de design.

    :::image type="content" source="media/paginated-reports-enter-data/paginated-design-view-matrix.png" alt-text="Captura de tela do relatório no modo de exibição de Design.":::

### <a name="run-the-report"></a>Executar o relatório

Para ver os valores reais e visualizar o relatório, execute-o.

1. Selecione **Executar** na faixa de opções **Página Inicial**.

    :::image type="content" source="media/paginated-reports-enter-data/paginated-run-report.png" alt-text="Captura de tela da seleção de Executar na faixa de opções Página Inicial.":::

    Agora você pode ver os valores. A matriz tem mais linhas do que você viu no modo de exibição de Design.  Você pode formatar a página ou decidir usar as configurações padrão antes de salvar o relatório no computador local ou publicá-lo no serviço.

1. Para ver como o relatório será exibido ao imprimi-lo, selecione **Layout de Impressão**.

    :::image type="content" source="media/paginated-reports-enter-data/paginated-select-print.png" alt-text="Captura de tela da seleção de Layout de Impressão.":::

    Agora ele é mostrado do modo como será exibido em uma página impressa.

    :::image type="content" source="media/paginated-reports-enter-data/paginated-print-layout.png" alt-text="Captura de tela do relatório no modo de exibição de layout de impressão.":::

## <a name="upload-the-paginated-report-to-the-power-bi-service"></a>Carregar um relatório paginado para o serviço do Power BI

Agora que há suporte para relatórios paginados no serviço do Power BI, você pode fazer upload de seu relatório paginado para uma capacidade Premium. Veja [Carregar um relatório paginado](paginated-reports-save-to-power-bi-service.md) para obter detalhes.

## <a name="upload-the-paginated-report-to-a-report-server"></a>Carregar o relatório paginado para um servidor de relatório

Você também pode carregar seu relatório paginado para um Servidor de Relatórios do Power BI ou o servidor de relatório SQL Server Reporting Services 2016 ou 2017. Antes de fazer isso, é preciso adicionar o item a seguir ao seu RsReportServer.config como uma extensão de dados adicionais. Faça backup do arquivo RsReportServer.config antes de fazer a alteração, caso encontre qualquer problema.

```xml
<Extension Name="ENTERDATA" Type="Microsoft.ReportingServices.DataExtensions.XmlDPConnection,Microsoft.ReportingServices.DataExtensions">
    <Configuration>
        <ConfigName>ENTERDATA</ConfigName>
    </Configuration>
</Extension>
```

Depois de editá-lo, é assim que a lista de provedores de dados no arquivo de configuração deve ser:

![Captura de tela do arquivo de configuração RsReportServer.](media/paginated-reports-enter-data/paginated-rsreportserver-config-file.png)

Isso é tudo. Agora você pode publicar relatórios que usam essa nova funcionalidade no seu servidor de relatório.

## <a name="next-steps"></a>Próximas etapas

- [O que são os relatórios paginados no Power BI Premium?](paginated-reports-report-builder-power-bi.md)
- [O que é o Servidor de Relatórios do Power BI?](../report-server/get-started.md)
