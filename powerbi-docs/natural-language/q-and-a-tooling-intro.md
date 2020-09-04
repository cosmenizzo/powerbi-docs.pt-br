---
title: Introdução à ferramenta de P e R para treinar a P e R do Power BI (versão prévia)
description: Introdução a ferramentas de P e R do Power BI
author: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/17/2020
ms.author: maggies
ms.openlocfilehash: aaa31851f338832a8c4f4fffb38f12414c859610
ms.sourcegitcommit: 13c4bec679313f2951f1833033316cb8176da8a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88937460"
---
# <a name="intro-to-qa-tooling-to-train-power-bi-qa-preview"></a>Introdução à ferramenta de P e R para treinar a P e R do Power BI (versão prévia)

Com as *ferramentas* de P e R do Power BI, você pode melhorar a experiência de idioma natural para seus usuários. Como um designer ou administrador, você interage com o mecanismo de linguagem natural e faz melhorias em três áreas: 

- Examinar as perguntas que seus usuários fizeram.
- Ensinar P e R para entender as perguntas.
- Gerenciar os termos que você ensinou ao P e R.

Além dessas funcionalidades de ferramenta dedicadas, a guia **Modelagem** no Power BI Desktop oferece mais opções:  

- Sinônimos
- Rótulos de linha
- Ocultar de P e R
- Configurando o esquema linguístico (avançado)

## <a name="get-started-with-qa-tooling"></a>Introdução à ferramenta de P e R

A ferramenta de P e R só está disponível no Power BI Desktop e, no momento, dá suporte apenas ao modo de importação.

1. Abra o Power BI Desktop e use P e R para criar um visual. 
2. No canto do visual, selecione o ícone de engrenagem. 

    ![Engrenagem de visual de P e R](media/q-and-a-tooling-intro/qna-visual-gear.png)

    A página guia de introdução é aberta.  

    ![Introdução a P e R](media/q-and-a-tooling-intro/qna-tooling-dialog.png)

### <a name="field-synonyms"></a>Campo Sinônimos

Selecione o **Campo Sinônimos** para conferir todas as tabelas e colunas que pertencem ao modelo. Essa exibição permite adicionar nomes alternativos para obter uma correspondência com as colunas com o objetivo de ajudar os usuários. Também é possível escolher se uma coluna ou tabela deve ser ocultada ou não de P e R.

![Página inicial do campo Sinônimos de P e R](media/q-and-a-tooling-intro/qna-tooling-field-synonyms-home.png)

Clique em uma das tabelas para expandir e uma caixa de diálogo semelhante à mostrada abaixo será exibida.

![Campo Sinônimos de P e R expandido](media/q-and-a-tooling-intro/qna-tooling-field-synonyms-expanded.png)

A caixa de diálogo mostrará todas as colunas e tabelas e os respectivos termos/sinônimos que os usuários podem usar ao fazer perguntas em relação ao conjunto de dados. É possível conferir rapidamente todos os termos em um só lugar e também adicionar ou remover termos de várias colunas. 

- Adicionar termos: caso tenha um campo chamado Vendas, será possível decidir adicionar um termo chamado Receita para que um usuário possa usar essa palavra em vez de ser solicitado a usar a palavra vendas. Clique no sinal de mais para adicionar um novo termo rapidamente

- Incluir em P e R: essa opção permite que uma coluna ou tabela seja omitida de P e R, o que significa que ela não será mostrada, tampouco um resultado poderá ser exibido com essa coluna. Lidar com datas é uma circunstância em que você pode decidir não incluir uma coluna. Caso haja vários campos de datas ou chaves estrangeiras, será possível decidir remover todos eles, exceto um dos campos de data, para que a coluna correta de data seja escolhida quando um usuário fizer uma pergunta relacionada à data.

- Termos sugeridos: a P e R também recomendará termos sugeridos recuperados do nosso mecanismo de sugestões para ajudar você a adicionar termos/sinônimos rapidamente. Caso as sugestões não sejam adicionadas, elas ainda funcionarão, porém exibirão uma linha pontilhada laranja ao usuário indicando que P e R considera ter uma resposta, mas não tem certeza. Caso o sinônimo sugerido esteja correto, clique no ícone + para que ele possa ser usado. Caso a sugestão esteja incorreta, clique no X para remover o termo e garantir que ele não seja usado como termo/sinônimo. Além disso, ele não funcionará dentro da P e R. As sugestões são fornecidas pelo Dicionário do Office e também são provenientes de renomeações encontradas dentro de um relatório

### <a name="review-questions"></a>Revisar perguntas

Selecione **Perguntas de revisão** para ver uma lista de conjuntos de valores que estão sendo usados no serviço do Power BI para seu locatário. A página **Perguntas de revisão** também exibe o proprietário do conjunto de dados, o workspace e a data da última atualização. Aqui, você pode selecionar um conjunto de dados e ver que perguntas os usuários estão fazendo. Os dados também mostram as palavras que não foram reconhecidas. Todos os dados mostrados aqui são dos últimos 28 dias.

![Perguntas de revisão de P e R](media/q-and-a-tooling-intro/qna-tooling-review-questions.png)

### <a name="teach-qa"></a>Treinar as perguntas e respostas

A seção **Ensinar P e R** permite treinar o P e R para reconhecer palavras. Para começar, você digita uma pergunta que contém uma ou mais palavras que o P e R não reconhece. O P e R solicita a definição desse termo. Insira um filtro ou um nome de campo que corresponda ao que a palavra representa. O P e R então reinterpreta a pergunta original. Se você estiver satisfeito com os resultados, poderá salvar sua entrada. Para saber mais, confira [Ensinar P e R](q-and-a-tooling-teach-q-and-a.md)

![Visualização de sinônimo de Ensinar P e R](media/q-and-a-tooling-intro/qna-tooling-teach-fixpreview.png)

### <a name="manage-terms"></a>Gerenciar termos

Tudo o que você salvou da seção Ensinar P e R aparece aqui, assim, você pode revisar ou excluir os termos que definiu. No momento, não é possível editar uma definição existente, portanto, para redefinir um termo, exclua e recrie-o.

![Gerenciar termos de P e R](media/q-and-a-tooling-intro/qna-manage-terms.png)

### <a name="suggest-questions"></a>Sugerir perguntas

> [!NOTE]
> As perguntas sugeridas serão exibidas para todas as instâncias do elemento visual de P e R. Não é possível criar um conjunto separado de sugestões para cada visual de P e R.
> 
> 

Sem fazer nenhuma configuração, o visual de P e R vai sugerir várias perguntas para começar. Essas perguntas são geradas automaticamente com base em seu modelo de dados. Em **Sugerir perguntas**, é possível substituir as perguntas geradas automaticamente com suas próprias perguntas.

Para iniciar, digite a pergunta que você deseja adicionar na caixa de texto. Na seção de visualização, você verá como será o resultado no visual de P e R. 

:::image type="content" source="media/q-and-a-tooling-intro/power-bi-qna-suggest-questions.png" alt-text="Sugerir perguntas de P e R":::
 
Selecione o botão **Adicionar** para adicionar essa pergunta a **Suas perguntas sugeridas**. Cada pergunta extra é adicionada ao final desta lista. As perguntas aparecerão no visual de P e R na mesma ordem que na lista. 

:::image type="content" source="media/q-and-a-tooling-intro/power-bi-qna-save-suggest-questions.png" alt-text="Salvar perguntas sugeridas":::
 
Selecione **Salvar** para mostrar a lista de perguntas sugeridas no visual de P e R. 

## <a name="other-qa-settings"></a>Outras configurações de P e R

### <a name="set-a-row-label"></a>Definir um rótulo de linha

Um rótulo de linha permite que você defina qual coluna (ou *campo*) melhor identifica uma única linha em uma tabela. Por exemplo, para uma tabela chamada "Cliente", o rótulo de linha geralmente é "Nome de Exibição". Fornecer esses metadados extras permite ao P e R plotar um visual mais útil quando os usuários digitam '"Mostrar vendas por cliente". Em vez de tratar "cliente" como uma tabela, ele pode usar "Nome de Exibição" e exibir um gráfico de barras mostrando as vendas de cada cliente. Você só pode definir a exibição de Modelagem do rótulo de linha. 

1. No Power BI Desktop, selecione modo de exibição Modelagem.

2. Selecione uma tabela para exibir o painel **Propriedades**.

3. Na caixa **Rótulo de linha**, selecione um campo.

## <a name="configure-the-linguistic-schema-advanced"></a>Configurar o esquema linguístico (avançado)

No Power BI, você pode treinar completamente e aprimorar o mecanismo de idioma natural dentro do P e R, incluindo a alteração da pontuação e a ponderação dos resultados do idioma natural subjacente. Para saber como, confira [Editar esquema linguístico do P e R e adicionar frases](q-and-a-tooling-advanced.md).

## <a name="next-steps"></a>Próximas etapas

Há diversas melhores práticas para melhorar o mecanismo de linguagem natural. Para obter mais informações, confira as [Melhores práticas de P e R](q-and-a-best-practices.md).
