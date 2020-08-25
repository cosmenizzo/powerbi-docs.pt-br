---
title: Permitir que os usuários personalizem visuais em um relatório
description: Permita que os leitores de relatório criem sua própria exibição de um relatório, sem editá-lo.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 08/12/2020
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 8dd6e64943ea05f2219efa471cd3fcfa4152650b
ms.sourcegitcommit: b60063c49ac39f8b28c448908ecbb44b54326335
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "88160431"
---
# <a name="let-users-personalize-visuals-in-a-report"></a>Permitir que os usuários personalizem visuais em um relatório

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Quando você compartilha um relatório com um público amplo, alguns de seus usuários podem querer ver exibições ligeiramente diferentes de visuais específicos. Talvez eles queiram trocar o que há no eixo, alterar o tipo de visual ou adicionar algo à dica de ferramenta. É difícil criar um visual que atenda aos requisitos de todos. Com essa nova funcionalidade, é possível capacitar seus consumidores para explorar e personalizar elementos visuais, tudo na exibição de leitura de relatório. Eles podem ajustar o visual da maneira que desejarem e salvá-lo como um indicador para verificar mais tarde. Eles não precisam ter permissão de edição para o relatório nem voltar para o autor do relatório para uma alteração.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-personalize-visual.png" alt-text="Personalizar um visual":::
 
## <a name="what-report-consumers-can-change"></a>O que os consumidores de relatório podem alterar

Esse recurso permite que os consumidores recebam insights adicionais por meio da exploração ad hoc de visuais em um relatório Power BI. Para saber como usar esse recurso como um consumidor, confira [Personalizar elementos visuais em seus relatórios](../consumer/end-user-personalize-visuals.md). O recurso é ideal para criadores de relatório que desejam habilitar cenários de exploração básica de seus leitores de relatório. Aqui estão as modificações que os leitores de relatório podem fazer:

- Altere o tipo de visualização
- Alternar uma medida ou dimensão
- Adicionar ou remover uma legenda
- Comparar duas ou mais medidas
- Alterar agregações etc.

Esse recurso não só permite novas funcionalidades de exploração, como inclui maneiras de os consumidores capturarem e compartilharem suas alterações:

- Capturar as alterações
- Compartilhar as alterações
- Redefinir todas as alterações de um relatório
- Redefinir todas as alterações de um visual
- Desmarcar as alterações recentes

## <a name="use-perspectives-for-a-more-focused-view"></a>Usar a opção Perspectivas para obter uma exibição mais focada

Para Personalizar elementos visuais é possível usar a opção **Perspectivas** com o objetivo de escolher o subconjunto de um modelo que fornecerá uma exibição mais focada. Escolher um subconjunto pode ser útil ao trabalhar com um grande modelo de dados. Isso permite se concentrar em um subconjunto de campos gerenciável e não sobrecarregar os leitores de relatório com uma coleção completa de campos nesse grande modelo. 

![Personalizar elementos visuais](media/power-bi-personalize-visuals/power-bi-personalize-perspective-01.png)

Lembre-se das seguintes considerações ao trabalhar com perspectivas:

* As perspectivas não devem ser usadas como um mecanismo de segurança, mas sim como uma ferramenta que fornece uma melhor experiência para o usuário final. Toda a segurança de uma perspectiva é herdada do modelo subjacente.

* As perspectivas são compatíveis com modelos de tabela e multidimensionais. No entanto, para perspectivas em modelos multidimensionais, somente será possível definir a perspectiva como sendo igual ao cubo da base do relatório.

* Antes de excluir a perspectiva de um modelo, certifique-se de verificar se ela não está sendo usada na experiência Personalizar elementos visuais. 

Para usar a opção Perspectivas é necessário habilitar Personalizar elementos visuais do relatório. Também é necessário criar pelo menos uma Perspectiva que inclua as dimensões e medidas com as quais deseja que os usuários finais interajam para obter a experiência de Personalizar elementos visuais.

Para criar a perspectiva, use o [Editor de Tabelas](https://tabulareditor.com/), que pode ser baixado do seguinte local: Baixar o Editor de Tabelas

Depois de instalar o **Editor de Tabelas**, abra o relatório no **Power BI Desktop** e inicie o **Editor de Tabelas** na guia **Ferramentas Externas** da faixa de opções, conforme mostrado na imagem a seguir.

![Editor de Tabelas na faixa de opções de Ferramentas Externas](media/power-bi-personalize-visuals/power-bi-personalize-perspective-02.png)

No Editor de Tabelas, clique com o botão direito do mouse na pasta **Perspectivas** para criar uma perspectiva.

![Criar uma pasta Perspectivas no Editor de Tabelas](media/power-bi-personalize-visuals/power-bi-personalize-perspective-03.png)

É possível clicar duas vezes no texto para renomear a perspectiva.

![Renomear a perspectiva](media/power-bi-personalize-visuals/power-bi-personalize-perspective-04.png)

Adicione campos à perspectiva abrindo a pasta **Tabelas** no Editor de Tabelas. Em seguida, clique com o botão direito do mouse nos campos que deseja exibir na perspectiva.

![Adicionar campos a uma perspectiva](media/power-bi-personalize-visuals/power-bi-personalize-perspective-05.png)

Repita esse processo para cada campo que deseja adicionar à perspectiva. Não é possível adicionar campos duplicados em uma perspectiva, portanto, todos os campos que já foram adicionados terão a opção Adicionar desabilitada.

Depois de adicionar todos os campos desejados, certifique-se de salvar as configurações no Editor de Tabelas e no Power BI Desktop.

![Salvar configurações de perspectivas no Editor de Tabelas e no Power BI Desktop](media/power-bi-personalize-visuals/power-bi-personalize-perspective-06.png)

Depois de salvar a nova perspectiva no modelo e salvar o relatório do Power BI Desktop, navegue até o painel **Formato** da página, onde será possível conferir uma nova seção para **Personalizar elementos visuais**.

![Seção Personalizar elementos visuais no painel Formatar](media/power-bi-personalize-visuals/power-bi-personalize-perspective-07.png)

A seleção da *Perspectiva do leitor de relatório* será definida inicialmente como *Campos padrão*. Depois de selecionar a seta suspensa, será possível conferir outras Perspectivas criadas.

![Selecione a seta suspensa para conferir outras perspectivas](media/power-bi-personalize-visuals/power-bi-personalize-perspective-08.png)

Depois de definir a Perspectiva da página do relatório, a experiência Personalizar elementos visuais dessa página será filtrada para a Perspectiva selecionada. Selecionar **Aplicar a todas as páginas** permite aplicar a configuração de Perspectiva a todas as páginas existentes em seu relatório.

![Selecione Aplicar a todas as páginas para que a perspectiva seja aplicada a todo o relatório](media/power-bi-personalize-visuals/power-bi-personalize-perspective-09.png)


## <a name="turn-on-the-preview-feature"></a>Ativar a versão prévia do recurso

Como esse recurso está em versão prévia, primeiro você precisa ativar a opção de recurso. Acesse **Arquivo** > **Opções e Configurações** > **Opções**. Em configurações **Globais** > **Versão prévia dos recursos**, verifique se a opção **Personalizar visuais** está selecionada.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-preview-personalize-visual.png" alt-text="Ativar Personalizar visuais":::

Talvez seja necessário reiniciar o Power BI Desktop para vê-lo nas configurações do arquivo atual.

## <a name="enable-personalization-in-a-report"></a>Habilitar personalização em um relatório

Depois de ativar a opção de visualização, você precisa habilitá-la especificamente para os relatórios para os quais você deseja que os consumidores possam personalizar os visuais.

Você pode habilitar o recurso no Power BI Desktop ou no serviço do Power BI.

### <a name="in-power-bi-desktop"></a>No Power BI Desktop

Para habilitar o recurso no Power BI Desktop, vá para **Arquivo** > **Opções e Configurações** > **Opções** > **Arquivo atual** > **Configurações de relatório**. Verifique se a opção **Personalizar visuais (versão prévia)** está ativada.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-report-settings-personalize-visual.png" alt-text="Habilitar personalização em um relatório":::

### <a name="in-the-power-bi-service"></a>No serviço do Power BI

Para habilitar o recurso no serviço do Power BI, vá para **Configurações** para seu relatório.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-report-service-settings-personalize-visual.png" alt-text="Configurações de relatório no serviço do Power BI":::

Ative **Personalizar visuais (versão prévia)**  > **Salvar**.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-report-service-personalize-visual.png" alt-text="Ativar Personalizar visuais no serviço":::

## <a name="select-visuals-that-can-be-personalized"></a>Selecionar visuais que podem ser personalizados

Quando você habilita essa configuração para um determinado relatório, por padrão, todos os visuais no relatório podem ser personalizados. Se você não quiser que todos os visuais sejam personalizados, poderá ativar ou desativar a configuração por visual.

Selecione o visual > selecione **Formato** no painel **Visualizações** > expanda **Cabeçalho de visual**.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-format-visual-header-personalize.png" alt-text="Selecionar cabeçalho de visual":::
 
Deslize **Personalizar visual** >  **Ligado** ou **Desligado**.

:::image type="content" source="media/power-bi-personalize-visuals/power-bi-format-visual-personalize-on-off.png" alt-text="Controle deslizante de Personalizar visual ligado ou desligado":::


## <a name="limitations-and-known-issues"></a>Limitações e problemas conhecidos

Atualmente, o recurso tem algumas limitações a serem consideradas.

- Não há suporte para esse recurso em cenários de inserção, incluindo publicar na Web.
- As explorações de usuário não persistem automaticamente. Você precisa salvar sua exibição como um indicador pessoal para capturar suas alterações.
- Esse recurso tem suporte nos aplicativos móveis do Power BI para tablets Android e iOS, e no aplicativo Power BI Windows. Não tem suporte nos aplicativos móveis do Power BI para telefones. No entanto, todas as alterações em um visual salvas em um indicador pessoal no serviço do Power BI são respeitadas em todos os aplicativos móveis do Power BI.

Há também alguns problemas conhecidos que estamos abordando:

- Não há suporte para a adição de hierarquia; você precisa adicionar os itens filho individuais.
- Não é possível alterar uma hierarquia de data para uma data ou vice-versa. 
- Com os indicadores pessoais, você pode obter resultados ligeiramente diferentes com base na sequência selecionada. Existe a possibilidade de discrepâncias porque não capturamos o estado completo do relatório, mas apenas as modificações feitas. A solução alternativa é selecionar **Redefinir para o padrão** e, em seguida, selecionar o indicador que você deseja exibir. 

## <a name="next-steps"></a>Próximas etapas

[Personalize os visuais em seus relatórios](../consumer/end-user-personalize-visuals.md).     

Experimente a nova experiência de personalização visual. Forneça seus comentários sobre esse recurso e como podemos continuar melhorando, [no site Power BI Ideas](https://ideas.powerbi.com/forums/265200-power-bi). 

Mais perguntas? [Experimente a Comunidade do Power BI](https://community.powerbi.com/)
