---
title: Usar ferramentas externas no Power BI (versão prévia)
description: Ampliar o uso do Power BI Desktop com ferramentas externas
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/15/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 4d752a49587e611c3f42de3f40c68437f36fe3a9
ms.sourcegitcommit: 11deeccf596e9bb8f22615276a152614f7579f35
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2020
ms.locfileid: "86411812"
---
# <a name="using-external-tools-in-power-bi-desktop-preview"></a>Usar ferramentas externas no Power BI Desktop (versão prévia)

A partir da versão de julho de 2020 do Power BI Desktop, você pode usar ferramentas externas para adicionar mais funcionalidade e valor ao Power BI Desktop. O suporte a ferramentas externas permite que você aproveite a variedade de ferramentas da comunidade dos Analysis Services para profissionais de BI, como otimização e criação de consulta/expressão DAX, além do ALM (Gerenciamento do Ciclo de Vida do Aplicativo).

A faixa de opções **Ferramentas Externas** no Power BI Desktop contém botões para ferramentas externas instaladas no computador e registradas no Power BI Desktop. As ferramentas externas iniciadas no Power BI Desktop são conectadas automaticamente ao mecanismo dos Analysis Services que funciona como parte do Power BI Desktop, fornecendo uma experiência contínua para os usuários.

![A faixa de opções de ferramentas externas no Power BI Desktop](media/desktop-external-tools/desktop-external-tools-01.png)

As seções a seguir descrevem as operações que têm suporte das ferramentas externas, uma lista de ferramentas em destaque incluídas no Power BI Desktop e instruções sobre como registrar ferramentas adicionais.

## <a name="supported-write-operations"></a>Operações de gravação compatíveis

As ferramentas externas podem se conectar ao conjunto de dados do Power BI Desktop (modelo dos Analysis Services) para editar os objetos a seguir. Não há suporte para a edição de um arquivo PBIT (modelo do Power BI Desktop).

* [Medidas](https://docs.microsoft.com/analysis-services/tabular-models/measures-ssas-tabular) para cálculos
* [Grupos de cálculos](https://docs.microsoft.com/analysis-services/tabular-models/calculation-groups) para reutilização de cálculo em modelos complexos
* [Perspectivas](https://docs.microsoft.com/analysis-services/tabular-models/perspectives-ssas-tabular) para definir exibições específicas de domínio comercial focadas de metadados dos conjuntos de dados

O gerenciamento de traduções de metadados usando ferramentas externas pode ser possível, mas não tem suporte atualmente nessa versão prévia. Se o local do usuário atual for um local traduzido, a edição de objetos na lista de campos não funcionará corretamente usando a versão atual do Power BI Desktop. 

Há um problema conhecido quando você cria relatórios em relação a modelos que têm grupos de cálculo definidos. Se o grupo de cálculo definir a formatação dinâmica dependendo do cálculo/da medida selecionada, essa formatação estará disponível atualmente apenas em visuais de tabela, matriz e cartão.

Todos os metadados do conjunto de dados de [Modelo de Objeto Tabular](https://docs.microsoft.com/analysis-services/tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo) podem ser acessados para fins somente leitura, mas os objetos não abordados na lista descrita no artigo [Modelo de Objeto Tabular](https://docs.microsoft.com/analysis-services/tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo) ainda não têm suporte para edição na instância dos Analysis Services do Power BI Desktop.


## <a name="featured-external-tools"></a>Ferramentas externas em destaque

As ferramentas open-source a seguir da comunidade funcionam com o Power BI Desktop. O instalador de cada ferramenta a registra com o Power BI Desktop na instalação:

* Tabular Editor
* DAX Studio
* Kit de ferramentas ALM

Vamos analisar cada ferramenta.

### <a name="tabular-editor"></a>Tabular Editor

Você pode instalar o [Tabular Editor](https://tabulareditor.com/) pelo seguinte link: [Site do Tabular Editor](https://tabulareditor.com/)

O Tabular Editor permite que profissionais de BI criem, mantenham e gerenciem facilmente modelos tabulares usando um editor leve e intuitivo. A exibição hierárquica mostra todos os objetos no modelo tabular, organizados por pastas de exibição, com suporte para edição de propriedades de seleção múltipla e realce de sintaxe DAX.

![Captura de tela do Tabular Editor](media/desktop-external-tools/desktop-external-tools-02.png)

O código-fonte do Tabular Editor pode ser encontrado no seguinte repositório GitHub: [Tabular Editor no GitHub](https://github.com/otykier/TabularEditor)

O autor da ferramenta principal do Tabular Editor é [Daniel Otykier](https://www.linkedin.com/in/daniel-otykier-2231876).


### <a name="dax-studio"></a>DAX Studio

Você pode instalar o [DAX Studio](https://daxstudio.org) pelo seguinte link: [Site do DAX Studio](https://daxstudio.org)

O DAX Studio é conhecido por ser uma ferramenta completa para criação, diagnóstico, ajuste de desempenho e análise de DAX. Seus recursos incluem navegação de objeto, rastreamento integrado, detalhamentos de execução de consulta com estatísticas detalhadas, realce e formatação da sintaxe DAX. A imagem a seguir mostra uma tela do DAX Studio. 

![Captura de tela do DAX Studio](media/desktop-external-tools/desktop-external-tools-03.png)

O código-fonte do DAX Studio pode ser encontrado no seguinte repositório GitHub: [DAX Studio no GitHub](https://github.com/DaxStudio/DaxStudio)

O autor da ferramenta principal do DAX Studio é [Darren Gosbell](https://www.linkedin.com/in/darrengosbell).

### <a name="alm-toolkit"></a>Kit de ferramentas ALM

Você pode instalar o [ALM Toolkit](http://alm-toolkit.com) pelo seguinte link: [Site do ALM Toolkit](http://alm-toolkit.com)

O ALM Toolkit é uma ferramenta de comparação de esquemas para conjuntos de dados do Power BI usada em cenários de ALM (Gerenciamento do Ciclo de Vida do Aplicativo). Com ele, você pode realizar a implantação simplificada entre ambientes e reter dados históricos de atualização incremental. Com o ALM Toolkit, você pode diferenciar e mesclar arquivos de metadados, ramificações e repositórios. Você também pode reutilizar definições comuns entre conjuntos de dados.

![Captura de tela do ALM Toolkit](media/desktop-external-tools/desktop-external-tools-04.png)

O código-fonte do ALM Toolkit pode ser encontrado no seguinte repositório GitHub: [ALM Toolkit no GitHub](https://github.com/microsoft/analysis-services)

O autor da ferramenta principal do ALM Toolkit é [Christian Wade](https://www.linkedin.com/in/christianwade1).


## <a name="how-to-register-external-tools"></a>Como registrar ferramentas externas

Para registrar outras ferramentas externas com o Power BI Desktop, crie um arquivo JSON com o seguinte conteúdo:

```json
{
    "name": "<tool name>",
    "description": "<tool description>",
    "path": "<tool executable path>",
    "arguments": "<optional command line arguments>",
    "iconData": "image/png;base64,<encoded png icon data>"
}
```

A seguinte lista descreve a lista de elementos no arquivo JSON:
 
* **name:** fornece um nome para a ferramenta, que aparece como uma legenda de botão na faixa de opções de Ferramentas Externas no Power BI Desktop.
* **description:** (opcional) fornece uma descrição, que será exibida como uma dica de ferramenta na faixa de opções de Ferramentas Externas do Power BI Desktop.
* **path:** fornece o caminho totalmente qualificado para o executável da ferramenta.
* **arguments:** (opcional) fornece uma cadeia de caracteres de argumentos da linha de comando com a qual o executável da ferramenta deve ser iniciado. Você pode usar qualquer um dos seguintes espaços reservados:
    * **%server%:** substituído pelo nome do servidor e número de porta da instância local do Tabular dos Analysis Services para modelos de dados importados/DirectQuery.
    * **%database%:** substituído pelo nome do banco de dados do modelo hospedado na instância local do Tabular dos Analysis Services para modelos de dados importados/DirectQuery.
* **iconData:** fornece dados da imagem, que serão renderizados como um ícone de botão na faixa de opções Ferramentas Externas no Power BI Desktop. A cadeia de caracteres deve ser formatada de acordo com a sintaxe para URIs de dados sem o prefixo "data:".
 
Nomeie o arquivo `"<tool name>.pbitool.json"` e coloque-o na seguinte pasta:

* `%commonprogramfiles%\Microsoft Shared\Power BI Desktop\External Tools`

Para ambientes de 64 bits, coloque os arquivos na seguinte pasta:

* **Arquivos de Programas (x86)\Common Files\Microsoft Shared\Power BI Desktop\External Tools**

Os arquivos nesse local especificado com a extensão **.pbitool.json** são carregados pelo Power BI Desktop na inicialização.


## <a name="next-steps"></a>Próximas etapas

Você também pode estar interessado nos seguintes artigos:

* [Usar o drill-through entre relatórios no relatório Power BI](desktop-cross-report-drill-through.md)
* [Usando segmentações no Power BI Desktop](../visuals/power-bi-visualization-slicers.md)


