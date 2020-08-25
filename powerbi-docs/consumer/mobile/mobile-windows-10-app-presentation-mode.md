---
title: Exibir o modo de apresentação no Surface Hub e no Windows 10 – Power BI
description: Leia sobre como mostrar relatórios do Power BI no Surface Hub e mostrar dashboards do Power BI, relatórios e blocos no modo de tela inteira em dispositivos com o Windows 10.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 08/12/2020
ms.author: painbar
ms.openlocfilehash: c4453f1475ac2ab227294b0b3bd8ba5dba10de67
ms.sourcegitcommit: 64139587061136a43c5aea3b6db4d1a94e4e7795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "88204486"
---
# <a name="view-reports-and-dashboards-in-presentation-mode-on-surface-hub-and-windows-10-devices"></a>Exibir relatórios e dashboards no modo de apresentação no Surface Hub e em dispositivos Windows 10
É possível usar o modo de apresentação para exibir relatórios e dashboards em tela inteira em dispositivos Windows 10 e no Surface Hub. O modo de apresentação é útil para a exibição do Power BI em reuniões ou conferências ou em um projetor dedicado no escritório ou até mesmo para maximizar o espaço em uma tela pequena.

![Relatório no modo de tela inteira](./media/mobile-windows-10-app-presentation-mode/power-bi-presentation-mode-2.png)

No modo de apresentação:
* Todos os "cromados" (como as barras de navegação e de menu) desaparecem, facilitando o foco nos dados de seu relatório.
* Uma barra de ferramentas de ação fica disponível para permitir que você interaja com seus dados e controle a apresentação.
* Você pode reproduzir uma apresentação de slides que circule automaticamente entre páginas e indicadores ou ambos.

>[!NOTE]
>O suporte de aplicativo móvel Power BI para **telefones que usam o Windows 10 Mobile** será descontinuado em 16 de março de 2021. [Saiba mais](https://go.microsoft.com/fwlink/?linkid=2121400)

## <a name="use-presentation-mode"></a>Usar modo de apresentação
No aplicativo móvel do Power BI, toque no ícone **Tela inteira** para ir para o modo de tela inteira.
![Ícone de tela inteira](././media/mobile-windows-10-app-presentation-mode/power-bi-full-screen-icon.png) O cromado do aplicativo desaparece, e uma barra de ferramentas de ação é exibida na parte inferior da tela ou nos lados esquerdo e direito (depende do tamanho da tela).

[![Relatório no modo de tela inteira com barras de ferramentas laterais](./media/mobile-windows-10-app-presentation-mode/power-bi-presentation-mode-toolbar.png)](./media/mobile-windows-10-app-presentation-mode/power-bi-presentation-mode-toolbar-expanded.png#lightbox)

Na barra de ferramentas, você pode tocar para executar as seguintes ações:

|||
|-|-|
|![ícone de voltar](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-back-icon.png)|**Voltar** à página anterior. Um toque longo no ícone exibirá as janelas de trilha, permitindo que você navegue até a pasta que contém seu relatório ou dashboard.|
|![Ícone de Paginação](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-pages-icon.png)|**Alternar páginas**, para ir a outra página do relatório na apresentação.|
|![Ícone de Indicadores](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-bookmarks-icon.png)|**Aplicar um indicador** para apresentar a exibição específica dos dados que o indicador captura. Você pode aplicar indicadores pessoais e de relatório.|
|![Ícone de Tinta](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-ink-icon.png)|**Escolher uma cor de tinta**, quando você usar a caneta do Surface para desenhar e fazer anotações em sua página de relatório.|
|![Ícone de Borracha](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-eraser-icon.png)|**Apagar marcas de tinta** que você pode ter feito com a caneta do Surface ao desenhar e fazer anotações na página de relatório.          |
|![Ícone de Redefinir](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-reset-icon.png)|**Redefinir para a exibição padrão** e desmarcar os filtros, as segmentações ou outras alterações na exibição de dados que você tenha feito durante a apresentação.|
|![Ícone Compartilhar](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-share-icon.png)|**Compartilhar** uma imagem do modo de exibição de apresentação com seus colegas. A imagem incluirá as anotações feitas com a caneta Surface durante a apresentação.|
|![Ícone de atualização](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-refresh-icon.png)|**Atualizar** o relatório.|
|![Ícone de reprodução](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-play-icon.png)|**Reproduzir a apresentação de slides**, ocultando a barra de ação e iniciando a apresentação de slides. Um seletor permite que você opte por girar automaticamente entre páginas e indicadores ou ambos. Por padrão, a apresentação de slides gira automaticamente entre as páginas uma vez a cada 30 segundos. Você pode alterar essas configurações em [**Configurações > Opções**](#slideshow-settings). Confira [mais detalhes](#slideshows) sobre apresentações de slides|
|![Sair do modo de tela inteira](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-exit-full-screen-icon.png)|**Sair** do modo de apresentação.|
|![Ícone de pesquisa](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-search-icon.png)|**Pesquisar** outros artefatos no Power BI.|

É possível desencaixar a barra de ferramentas, arrastá-la e soltá-la em qualquer lugar da tela. Isso é útil para grandes telas, quando você desejar se concentrar em uma área específica em seu relatório e desejar ter as ferramentas disponíveis ao lado dela. Basta colocar o dedo na barra de ferramentas e passá-la para a tela de relatório.

[![Relatório no modo de apresentação e barra de ferramentas desencaixada](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-drag-toolbar-2.png)](./media/mobile-windows-10-app-presentation-mode/power-bi-windows-10-presentation-drag-toolbar-2-expanded.png#lightbox)

## <a name="slideshows"></a>Apresentações de slides

É possível configurar a apresentação de slides para ser reproduzida automaticamente. Você pode defini-la para percorrer as páginas e os indicadores ou ambos.

Quando você seleciona o botão **Reproduzir** na barra de ferramentas de ação, a apresentação de slides é iniciada. É exibido um controle que permite pausar a apresentação de slides ou alterar o que está sendo reproduzido: páginas, indicadores ou ambos.

![Captura de tela do seletor de apresentação de slides](././media/mobile-windows-10-app-presentation-mode//power-bi-windows-10-slideshow-selector.png)

 O controlador mostra o nome da exibição mostrada no momento (página ou indicador e página). Na imagem acima, vemos que, no relatório chamado **Vendas**, estamos exibindo o indicador **Pacífico Asiático** na página **Desempenho de Vendas**.

Por padrão, uma apresentação de slides reproduz somente páginas, a uma taxa de 1 página a cada 30 segundos. O comportamento padrão nas [Configurações de apresentação de slides](#slideshow-settings).


### <a name="auto-play-a-slideshow-on-startup"></a>Reprodução automática de uma apresentação de slides na inicialização

É possível configurar o aplicativo móvel do Power BI para iniciar a reprodução de uma apresentação de slides de modo automático, sempre que o aplicativo for iniciado. Essa opção é útil para criar uma experiência semelhante a um quiosque que executa um relatório em exibições públicas, sem intervenção manual. Confira a opção [Configurações de apresentação de slides](#slideshow-settings) para obter detalhes sobre como configurar um relatório para reprodução automática.

### <a name="slideshow-settings"></a>Configurações da apresentação de slides

Por padrão, uma apresentação de slides reproduz somente páginas, a uma taxa de 1 página a cada 30 segundos. É possível alterar esse comportamento padrão acessando **Configurações > Opções**, conforme ilustrado abaixo. Também é possível ativar a reprodução automática e escolher um relatório para reprodução.

1. Selecione o ícone Configurações.

1. Abra a guia Opções.

1. É possível alterar as configurações padrão para selecionar como a apresentação de slides será exibida (páginas, indicadores ou ambos) e a frequência da transição dos slides.

1. Caso queira que o relatório comece a ser reproduzido automaticamente quando o aplicativo for iniciado, ative a alternância e escolha **Selecionar Relatório**. Será possível pesquisar os relatórios aos quais você tem acesso.

![Captura de tela das configurações de apresentação de slides](././media/mobile-windows-10-app-presentation-mode//power-bi-windows-10-slideshow-settings.png)

## <a name="next-steps"></a>Próximas etapas
* [Exibir painéis e relatórios no modo de tela inteira do serviço do Power BI](../end-user-focus.md)
* Dúvidas? [Experimente perguntar para a Comunidade do Power BI](https://community.powerbi.com/)