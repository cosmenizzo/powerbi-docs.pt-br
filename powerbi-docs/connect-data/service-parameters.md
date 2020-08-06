---
title: Editar configurações de parâmetro no serviço do Power BI
description: Os parâmetros de consulta são criados no Power BI Desktop, mas podem ser examinados e atualizados no serviço do Power BI
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 08/04/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 3b64c1dd502fd16199fbff9f64cd2c017006d1f1
ms.sourcegitcommit: a7227f6d3236e6e0a7bc1f83ff6099b5cd58bff3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87768464"
---
# <a name="edit-parameter-settings-in-the-power-bi-service"></a>Editar configurações de parâmetro no serviço do Power BI
Criadores de relatório adicionam parâmetros de consulta a relatórios no Power BI Desktop. Os parâmetros permitem que eles façam que partes dos relatórios dependam de um ou mais *valores* de parâmetro. Por exemplo, um criador de relatórios pode criar um parâmetro que restringe os dados a um único país/região ou um parâmetro que define os formatos aceitáveis para campos como datas, hora e texto.

![Guia Início mostrando a opção Gerenciar parâmetros no Desktop](media/service-parameters/power-bi-manage-parameters.png)

## <a name="review-and-edit-parameters-in-power-bi-service"></a>Revisar e editar parâmetros no serviço do Power BI

Como criador do relatório, é possível definir parâmetros no Power BI Desktop. Quando você [publica o relatório para o serviço do Power BI](../create-reports/desktop-upload-desktop-files.md), as seleções e as configurações de parâmetro vão com ele. É possível examinar e editar configurações de parâmetro no serviço do Power BI, mas não criá-las.

1. No serviço do Power BI, selecione o ícone de engrenagem ![ícone de engrenagem](media/service-parameters/power-bi-cog.png) e escolha **Configurações**.

2. Selecione a guia para os **Conjuntos de dados** e destaque um conjunto de dados na lista. 
    
    ![Janela Configurações com a guia Conjuntos de dados selecionada](media/service-parameters/power-bi-select-dataset2.png)

3. Expanda **Parâmetros**.  Se o conjunto de dados selecionado não tiver parâmetros, você verá uma mensagem com um link para saber mais sobre os parâmetros de consulta. Se o conjunto de dados tiver parâmetros, expanda o título **Parâmetros** para revelá-los. 

    ![Janela Configurações com a guia Parâmetros expandida](media/service-parameters/power-bi-settings.png)

    Examine as configurações do parâmetro e faça alterações, se necessário. Campos esmaecidos não são editáveis. 


## <a name="next-steps"></a>Próximas etapas
Um modo específico para adicionar parâmetros simples é [modificando a URL](../collaborate-share/service-url-filters.md).
