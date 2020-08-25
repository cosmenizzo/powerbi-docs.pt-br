---
title: Atualização automática de página no Power BI Desktop
description: Este artigo mostra como atualizar automaticamente as páginas para fontes do DirectQuery no Power BI Desktop.
author: davidiseminger
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 08/13/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 070dfd4048c494f9a1865603be4e692231f771f5
ms.sourcegitcommit: 9b193dc155a306738a23b6bf20bcc424b8c64afd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/15/2020
ms.locfileid: "88247130"
---
# <a name="automatic-page-refresh-in-power-bi"></a>Atualização automática de página no Power BI

Ao monitorar eventos críticos, é importante que os dados sejam atualizados no mesmo momento que os dados de origem. Por exemplo, no setor de manufatura, é essencial saber quando um computador está com problemas de funcionamento ou prestes a ter esse tipo de problema. Caso esteja monitorando sinais, como sentimentos em mídias sociais, você desejará saber sobre alterações repentinas no momento em que elas acontecerem.

A atualização automática de página no Power BI permite que a página ativa do relatório consulte novos dados de [fontes do DirectQuery](../connect-data/desktop-directquery-about.md), em uma cadência predefinida.

## <a name="refresh-types"></a>Tipos de atualização

Ao usar a atualização automática de página, há dois tipos de atualização disponíveis: intervalo fixo e detecção de alterações.

### <a name="fixed-interval"></a>Intervalo fixo

Esse tipo de atualização permite atualizar todos os elementos visuais em uma página de relatório com base em um intervalo constante, como um segundo ou cinco minutos. Quando esse intervalo específico é atingido, todos os elementos visuais da página enviam uma consulta de atualização para a fonte de dados e realizam a atualização de maneira correspondente.

### <a name="change-detection"></a>Detecção de alteração

Esse tipo de atualização permite atualizar elementos visuais em uma página com base na detecção de alterações nos dados, em vez de usar um intervalo de atualização específico. Essa medida pesquisa alterações especificamente em sua [fonte do DirectQuery](../connect-data/desktop-directquery-about.md). Além de definir a medida, também é necessário selecionar com que frequência o Power BI Desktop verificará se há alterações. Ao publicar no serviço, esse tipo de atualização será compatível somente com workspaces que fazem parte de uma capacidade Premium.

## <a name="authoring-reports-with-automatic-page-refresh-in-power-bi-desktop"></a>Como criar relatórios usando a atualização automática de página no Power BI Desktop

A atualização automática de página está disponível somente para [fontes do DirectQuery](../connect-data/desktop-directquery-about.md), portanto, ela estará disponível apenas quando você estiver conectado a uma fonte de dados do DirectQuery. Essa restrição se aplica aos dois tipos de atualização automática de página.

Para usar a atualização automática de página no Power BI Desktop, selecione a página do relatório para a qual deseja habilitar a atualização automática de página. No painel **Visualizações**, selecione o botão **Formatação** (um rolo de pintura) e localize a seção **Atualização de página**, próxima à parte inferior do painel.

![Local de atualização de página](media/desktop-automatic-page-refresh/automatic-page-refresh-01.png)

1. Ativa ou desativa a atualização da página.
2. Tipo de atualização
3. Entradas e informações (dependendo do tipo de atualização)

O cartão **Atualizar página** estará disponível somente se você estiver conectado a uma [fonte do DirectQuery](../connect-data/desktop-directquery-about.md). Para habilitar a atualização automática de página, a alternância precisa estar na posição Ativada. As entradas necessárias e as informações fornecidas dependerão do tipo de atualização selecionado.

### <a name="fixed-interval-setup"></a>Configuração do intervalo fixo

Ao selecionar **Atualização automática de página** como o tipo de atualização, será necessário fornecer o intervalo de atualização desejado. O valor padrão é de 30 minutos. (O intervalo de atualização mínimo é de um segundo). O relatório começará a ser atualizado no intervalo que você definir.

Ao clicar em Mostrar detalhes, o Power BI fornecerá informações adicionais sobre:

- Se o recurso for habilitado pelo administrador (somente quando conectado à sua conta do Power BI)
- O intervalo mínimo permitido pelo administrador (somente quando conectado à sua conta do Power BI)
- A taxa real de atualização (geralmente maior do que o intervalo selecionado)
- O horário da última atualização

![Mostrar detalhes da atualização de página](media/desktop-automatic-page-refresh/automatic-page-refresh-02.png)

### <a name="change-detection-setup"></a>Configuração da detecção de alterações

Ao selecionar **Detecção de alterações** como o tipo de atualização, um link será exibido para **Adicionar a detecção de alterações**. Também é possível acessar a janela **Detecção de alterações** da guia Modelagem na faixa de opções. Clique no ícone **Detecção de alterações** na seção **Atualização de página**. Por fim, é possível clicar com o botão direito do mouse ou selecionar a seta suspensa ao lado de qualquer valor na caixa Valores e selecionar **Detecção de alterações** no menu.

![Cartão de detecção de alterações](media/desktop-automatic-page-refresh/automatic-page-refresh-03.png)

Depois que a janela estiver aberta, será exibida a opção **Tipo de medida** em que é possível selecionar uma medida existente ou criar uma do zero. Ao selecionar uma existente, basta clicar na medida desejada na lista de campos ou arrastá-la e soltá-la na seção **Escolher medida existente**. Ao criar uma medida, será possível **Escolher um cálculo** para ela entre contagem, contagem distinta, mínimo, máximo e soma. Por exemplo: é possível usar uma contagem distinta para contar IDs de clientes e atualizar somente quando um novo cliente for adicionado à lista. Depois de selecionar uma medida, será necessário definir com que frequência o Power BI poderá **Verificar se há alterações**. Esse será o intervalo da frequência com que o Power BI calculará a medida e pesquisará as alterações. Depois de clicar em aplicar, uma nova medida será exibida na lista Campos com o ícone de detecção de alterações.

![Janela da detecção de alterações](media/desktop-automatic-page-refresh/automatic-page-refresh-04.png)

Ao retornar para a seção de atualização de página, serão exibidas informações sobre qual medida está sendo usada para a detecção de alterações e o intervalo definido para sua referência.

![Cartão da detecção de alterações com detalhes](media/desktop-automatic-page-refresh/automatic-page-refresh-05.png)

> [!NOTE]
> Somente uma medida de detecção de alterações será permitida por modelo.

## <a name="determining-the-refresh-interval"></a>Como determinar o intervalo de atualização

Quando a atualização automática de página está habilitada, o Power BI Desktop envia constantemente consultas para sua fonte do DirectQuery. Depois que a consulta é enviada, há um atraso antes que os dados sejam retornados. Portanto, em intervalos de atualização curtos, você deve confirmar se as consultas retornam os dados consultados dentro do intervalo configurado. Se os dados não forem retornados dentro do intervalo, os visuais serão atualizados com menos frequência do que o configurado.

Essas considerações se aplicam aos dois tipos de atualização: intervalo fixo e detecção de alterações. A principal diferença é que na detecção de alterações somente uma consulta voltará para a fonte em um intervalo fixo. Além disso, a atualização de elementos visuais será disparada somente quando o valor da medida de detecção de alterações for alterado.

Como prática recomendada, o intervalo de atualização deve corresponder ao menos à sua nova taxa de chegada de dados esperada:

* Se os dados novos chegarem à fonte a cada 20 minutos, o intervalo de atualização não poderá ser inferior a 20 minutos.
* Se novos dados chegarem a cada segundo, defina o intervalo para um segundo.

Em intervalos de baixa atualização, como um segundo, considere os seguintes fatores:

- O tipo da fonte de dados do DirectQuery
- A carga que suas consultas criam nele
- A distância dos visualizadores de relatório do datacenter da capacidade

É possível estimar os tempos de retorno usando o [Performance Analyzer](desktop-performance-analyzer.md) no Power BI Desktop, bem como o menu Mostrar detalhes na seção de atualização de página para o tipo de atualização de intervalo fixo. O Performance Analyzer permite verificar se cada consulta de visual tem tempo suficiente para voltar com resultados da fonte. Ele também permite que você determine onde o tempo é gasto. Com base nos resultados do Performance Analyzer, você pode ajustar a fonte de dados ou experimentar outros visuais e medidas em seu relatório.

Esta imagem mostra os resultados de uma fonte do DirectQuery no Performance Analyzer:

![Resultados do Performance Analyzer](media/desktop-automatic-page-refresh/automatic-page-refresh-06.png)

Vamos considerar algumas outras características dessa fonte de dados:

- Os dados chegam a obter uma taxa de 2 segundos
- O Performance Analyzer mostra a consulta máxima + o tempo de exibição de aproximadamente 4,9 segundos (4.688 milissegundos)
- A fonte de dados está configurada para lidar com aproximadamente 1.000 consultas simultâneas por segundo
- É esperado que aproximadamente 10 usuários exibam o relatório simultaneamente

Isso resulta na seguinte equação:

- **5 visuais x 10 usuários = aproximadamente 50 consultas**

O resultado desse cálculo mostra muito mais carga do que a fonte de dados consegue suportar. Os dados chegam a uma taxa de dois segundos, de modo que essa deve ser a taxa de atualização. Porém, como a consulta leva cerca de cinco segundos para ser concluída, você deve defini-la como mais de cinco segundos.

Observe também que esse resultado pode ser diferente quando você publica o relatório no serviço. Essa diferença ocorre porque o relatório usará a instância do Azure Analysis Services hospedada na nuvem. Talvez você queira ajustar suas taxas de atualização de acordo com isso.

Para considerar as consultas e atualizar o tempo, o Power BI só executará a próxima consulta de atualização quando todas as consultas de atualização restantes forem concluídas. Portanto, mesmo que o intervalo de atualização seja menor do que o tempo que suas consultas levam para serem processadas, o Power BI só será atualizado novamente quando as consultas restantes forem concluídas.

No caso do tipo de atualização de detecção de alterações, essas considerações ainda se aplicam. Além disso, o [Performance Analyzer](desktop-performance-analyzer.md) mostrará os resultados da consulta da medida de detecção de alterações, mesmo que eles não correspondam a nenhum elemento visual em seu relatório. Fornecemos essa funcionalidade para que seja possível solucionar problemas desse tipo específico de medida, seguindo as mesmas diretrizes mencionadas anteriormente. A principal diferença desse tipo de atualização é que somente uma consulta será enviada para a fonte de dados, em vez de todas as consultas de todos os elementos visuais. Isso também ocorrerá caso vários usuários estejam exibindo o relatório.

![Resultados do Performance Analyzer com a detecção de alterações](media/desktop-automatic-page-refresh/automatic-page-refresh-07.png)

Para o mesmo cenário discutido anteriormente:

- **Uma consulta da medida de detecção de alterações para 5 elementos visuais gerará somente uma consulta para qualquer número de visualizadores**

- **Quando a medida de detecção de alterações disparar uma atualização, supondo que o cenário seja igual ao anterior, o resultado será 5 elementos visuais x 10 usuários = 50 consultas, aproximadamente**

Em resumo, ao usar a detecção de alterações, somente uma consulta será enviada para a fonte de dados até que uma alteração seja detectada. Quando isso acontecer, a mesma lógica usada para o tipo de atualização de intervalo fixo aplicará a atualização de todos os elementos visuais para todos os usuários, gerando o mesmo número de consultas. Essa abordagem deverá ser mais eficiente a longo prazo.

Agora, vamos examinar como é possível detectar e diagnosticar problemas de desempenho como um administrador de capacidade. Você também pode conferir a seção [Perguntas frequentes](#frequently-asked-questions), mais adiante neste artigo, para ver mais perguntas e respostas sobre desempenho e solução de problemas.

## <a name="automatic-page-refresh-in-the-power-bi-service"></a>Atualização automática de página no serviço do Power BI

Também é possível definir a atualização automática de página para relatórios que foram publicados no serviço do Power BI, contanto que a fonte de dados esteja no [DirectQuery](../connect-data/desktop-directquery-about.md).

Para configurar a atualização automática de página para relatórios no serviço do Power BI, as etapas serão semelhantes às do Power BI Desktop. Quando configurada no serviço do Power BI, a atualização automática de página também é compatível com o conteúdo do [Power BI inserido](../developer/embedded/embedding.md). A seguinte imagem mostra a configuração de **Atualização de página** para o serviço do Power BI:

![Local da atualização de página no serviço](media/desktop-automatic-page-refresh/automatic-page-refresh-08.png)

1. Ativa ou desativa a atualização da página.
2. Tipo de atualização
3. Entradas e informações (dependendo do tipo de atualização)

> [!NOTE]
> Ao publicar o relatório com a atualização automática de página habilitada do Power BI Desktop para o serviço, você precisará fornecer as credenciais para a fonte de dados do DirectQuery no menu de configurações do conjunto. É possível configurar credenciais para que os visualizadores de relatórios acessem essa fonte de dados com identidades próprias, respeitando todas as configurações de segurança da fonte. No caso da medida de detecção de alterações, ela sempre será avaliada com as credenciais do autor.

### <a name="page-refresh-intervals"></a>Intervalos de atualização de página

Os tipos e intervalos da atualização de página permitidos no serviço do Power BI serão afetados pelo tipo de workspace do relatório. Isso se aplicará a estes relatórios:

* Publicar um relatório em um workspace com atualização automática de página habilitada
* Editar um intervalo de atualização de página que já esteja em um workspace
* Criar um relatório diretamente no serviço

O Power BI Desktop não tem restrições para intervalos de atualização e a frequência pode ser a cada segundo. No entanto, quando os relatórios são publicados no serviço do Power BI, determinadas restrições se aplicarão. Elas serão descritas nas seções a seguir.

### <a name="restrictions-on-refresh-intervals"></a>Restrições em intervalos de atualização

No serviço do Power BI, as restrições da atualização automática de página se aplicam com base no workspace em que o relatório é publicado, caso esteja usando os serviços Premium e as configurações de administrador da capacidade Premium.

Para esclarecer como essas restrições funcionam, vamos começar com um pouco de contexto sobre capacidades e workspaces.

As *capacidades* são um conceito importante do Power BI. Elas representam um conjunto de recursos (armazenamento, processador e memória) que são usados para hospedar e fornecer conteúdo do Power BI. As capacidades são compartilhadas ou dedicadas. Uma *capacidade compartilhada* é dividida com outros clientes da Microsoft. Uma *capacidade dedicada* está totalmente comprometida com um único cliente. Para obter uma introdução sobre capacidades dedicadas, confira [Gerenciar capacidades Premium](../admin/service-premium-capacity-manage.md).

Na capacidade compartilhada, as cargas de trabalho são executadas em recursos computacionais compartilhados com outros clientes. Como a capacidade precisa compartilhar recursos, as limitações são impostas para garantir o *equilíbrio*, como definir o tamanho máximo do modelo (1 GB) e a frequência máxima de atualização diária (oito vezes por dia).

Os *workspaces* do Power BI residem em capacidades. Eles representam contêineres de segurança, de colaboração e de implantação. Cada usuário do Power BI tem um workspace pessoal, conhecido como **Meu workspace**. Workspaces adicionais podem ser criados para habilitar a colaboração e a implantação. Eles são conhecidos como *workspaces*. Por padrão, os workspaces, incluindo os pessoais, são criados na capacidade compartilhada.

Confira alguns detalhes dos dois cenários de workspaces:

**W compartilhados**. Em workspaces normais (que não fazem parte de uma capacidade Premium), a atualização automática de página tem um intervalo mínimo de 30 minutos (o menor intervalo permitido). O tipo de atualização de detecção de alterações não está disponível em capacidades compartilhadas.

**Workspaces Premium**. A disponibilidade da atualização automática de página nos workspaces Premium (para o intervalo fixo e a detecção de alterações) depende das configurações da carga de trabalho que o administrador Premium configurou para a capacidade Premium do Power BI. Há duas variáveis que podem afetar a capacidade de configurar a atualização automática de página:

 - **Ativar/desativar recurso**. Se o administrador da capacidade tiver desabilitado o recurso, você não conseguirá configurar nenhum tipo de atualização de página em seu relatório publicado. O intervalo fixo e a detecção de alterações podem ser ativados e desativados de maneira separada.

 - **Intervalo mínimo de atualização**. Ao habilitar a atualização automática de página para obter um intervalo fixo, o administrador de capacidade deverá configurar um intervalo mínimo de execução (o valor padrão é de cinco minutos). Se o intervalo for menor do que o mínimo, o serviço do Power BI substituirá o intervalo para respeitar o intervalo mínimo definido pelo administrador de capacidade.

 - **Intervalo mínimo de execução**. Ao habilitar a detecção de alterações, o administrador de capacidade deverá configurar um intervalo mínimo de execução (o valor padrão é de cinco segundos). Se o intervalo for menor do que o mínimo, o serviço do Power BI substituirá o intervalo para respeitar o intervalo mínimo definido pelo administrador de capacidade.

![Configurações de atualização automática de página no portal de administração de capacidade](media/desktop-automatic-page-refresh/automatic-page-refresh-09.png)

Esta tabela descreve com mais detalhes onde esse recurso está disponível e os limites para cada tipo de capacidade e [modo de armazenamento](../connect-data/service-dataset-modes-understand.md):

| Modo de armazenamento | Capacidade dedicada | Capacidade compartilhada |
| --- | --- | --- |
| DirectQuery | **FI compatível**: Sim <br>**CD compatível**: Sim <br>**Mínimo**: Um segundo <br>**Substituição do administrador**: Sim | **FI compatível**: Sim <br>**CD compatível**: Não <br>**Mínimo**: 30 minutos <br>**Substituição do administrador**: Não |
| Importar | **FI compatível**: Não <br>**CD compatível**: Não <br>**Mínimo**: N/D <br>**Substituição do administrador**: N/D | **FI compatível**: Não <br>**CD compatível**: Não <br>**Mínimo**: N/D <br>**Substituição do administrador**: N/D |
| Modo misto (DirectQuery + outras fontes de dados) | **FI compatível**: Sim <br>**CD compatível**: Sim <br>**Mínimo**: Um segundo <br>**Substituição do administrador**: Sim | **FI compatível**: Sim <br>**CD compatível**: Não <br>**Mínimo**: 30 minutos <br>**Substituição do administrador**: Não |
| Live Connect | **FI compatível**: Não <br>**CD compatível**: Não <br>**Mínimo**: N/D <br>**Substituição do administrador**: N/D | **FI compatível**: Não <br>**CD compatível**: Não <br>**Mínimo**: N/D <br>**Substituição do administrador**: N/D |
| Live Connect PBI | **FI compatível**: Não <br>**CD compatível**: Não <br>**Mínimo**: N/D <br>**Substituição do administrador**: N/D | **FI compatível**: Não <br>**CD compatível**: Não <br>**Mínimo**: N/D <br>**Substituição do administrador**: N/D |

*Legenda da tabela:*
1. *FI: intervalo fixo*
2. *CD: detecção de alterações*

## <a name="considerations-and-limitations"></a>Considerações e limitações

Há alguns lembretes importantes ao usar a atualização automática de página, seja no Power BI Desktop ou no serviço do Power BI:

* Os modos de armazenamento Importar, Live Connect e Push não dão suporte à atualização automática de página.  
* Há suporte para modelos compostos com pelo menos uma fonte de dados do DirectQuery.
* O Power BI Desktop não tem restrições para intervalos de atualização. A frequência do intervalo pode ser a cada segundo para os tipos de atualização de intervalo fixo e detecção de alterações. Quando os relatórios são publicados no serviço do Power BI, determinadas restrições se aplicam, conforme descrito [anteriormente](#restrictions-on-refresh-intervals) neste artigo.
* É possível ter somente uma medida de detecção de alterações por conjunto de dados.
* Somente pode haver um número máximo de 10 modelos com a medida de detecção de alterações em um locatário do Power BI.

### <a name="performance-diagnostics"></a>Diagnósticos de desempenho

A atualização automática de página é útil para monitorar cenários e explorar dados de alteração rápida. Mas, às vezes, isso pode colocar uma carga indevida na capacidade ou na fonte de dados.

Para evitar a carga indevida em fontes de dados, o Power BI disponibiliza estas proteções:

- Todas as consultas de atualização automática de página são executadas em uma prioridade inferior para garantir que as consultas interativas (como carregamento de página e visuais de filtragem cruzada) tenham precedência.
- Se uma consulta não for concluída antes do próximo ciclo de atualização, o Power BI não emitirá novas consultas de atualização até que a consulta anterior seja concluída. Por exemplo, se você tiver um intervalo de atualização de um segundo e as consultas demorarem quatro segundos em média, o Power BI emitirá efetivamente apenas uma consulta a cada quatro segundos.

Há duas áreas nas quais você ainda pode encontrar gargalos de desempenho:

1. **A capacidade**. A consulta atinge primeiro a capacidade Premium, que dobrará e avaliará a consulta DAX gerada a partir das visualizações de relatório nas consultas de origem.
2. **A fonte de dados do DirectQuery**. as consultas traduzidas na etapa anterior são executadas em relação à origem. A fonte seria suas instâncias do SQL Server, fontes do SAP Hana e assim por diante.

Usando o [aplicativo de Métricas de Capacidade Premium](../admin/service-admin-premium-monitor-capacity.md), disponível para administradores, você pode visualizar quanto da capacidade está em uso por consultas de baixa prioridade.

Esse tipo de consulta inclui consultas de atualização automática de página e de atualização de modelo. Atualmente, não há como distinguir entre a carga de consultas de atualização automática de página e de atualização de modelo.

Se você observar que sua capacidade está ficando sobrecarregada com consultas de baixa prioridade, poderá executar as seguintes ações:

- Solicite um SKU premium maior.
- Peça ao proprietário do relatório para diminuir o intervalo de atualização.
- No portal de administração de capacidade, você pode:
   - Desative a atualização automática de página para essa capacidade.
   - Elevar o intervalo mínimo de atualização, o que afetará a todos os relatórios nessa capacidade.


### <a name="frequently-asked-questions"></a>Perguntas frequentes

**Sou autor de relatório. Defini o intervalo de atualização do relatório como um segundo no Power BI Desktop, mas, depois da publicação, meu relatório não está sendo atualizado no serviço.**

* Verifique se a atualização automática está ativada para a página. Como essa configuração é definida por página, você precisa garantir que ela esteja ativada para cada página do relatório que deseja atualizar.
* Verifique se você carregou em um workspace com uma capacidade Premium anexada. Caso contrário, seu intervalo de atualização será bloqueado em 30 minutos para o intervalo fixo e não estará disponível para a detecção de alterações.
* Se o relatório estiver em um workspace Premium, pergunte ao administrador se esse recurso está habilitado para a capacidade anexada. Além disso, certifique-se de que o intervalo mínimo de atualização para a capacidade seja igual ou menor do que o intervalo do relatório. Isso se aplicará de maneira separada para o intervalo fixo e a detecção de alterações

**Sou administrador de uma capacidade. Alterei as configurações do meu intervalo de atualização de página automático, mas as alterações não são refletidas. Ou seja, os relatórios ainda são atualizados em uma taxa incorreta ou não são atualizados, mesmo que eu tenha ativado a atualização automática da página.**

* Demora até cinco minutos para a atualização automática de página feita na interface do usuário do administrador de capacidade ser propagada para os relatórios.
* Além de ativar a atualização automática de página para a capacidade, você também precisará ativá-la para as páginas de um relatório em que deseja habilitá-la.
* Os dois tipos de atualização são gerenciados de maneira separada, portanto, certifique-se de que o tipo de atualização que você está habilitando está ativado.

**Meu relatório está operando no modo misto. (O modo misto significa que o relatório tem uma conexão DirectQuery e uma fonte de dados de importação). Alguns visuais não estão sendo atualizados.**

- Caso os elementos visuais façam referência a tabelas de Importar, esse comportamento é esperado. O modo Importar não dá suporte à atualização automática de página.
- Confira a primeira pergunta nesta seção.

**A atualização do meu relatório estava funcionando bem no serviço e, de repente, parou.**

* Tente atualizar a página para ver se o problema se resolve sozinho.
* Fale com seu administrador de capacidade. O administrador pode ter desativado o recurso ou gerado o intervalo mínimo de atualização. (Confira a segunda pergunta nesta seção).

**Sou autor de relatório. Meus visuais não estão sendo atualizados na frequência que especifiquei. A atualização está ocorrendo em uma taxa mais lenta.**

* Se as consultas estiverem demorando mais para serem executadas, seu intervalo de atualização será atrasado. A atualização automática de página aguarda a conclusão de todas as consultas antes de executar novas.
* Pode ser que seu administrador de capacidade tenha definido um intervalo de atualização mínimo maior do que aquele que você definiu em seu relatório. Peça ao administrador de capacidade para reduzir o intervalo mínimo de atualização.

**As consultas de atualização automática de página são atendidas pelo cache?**

* Não. Todas as consultas de atualização automática de página ignoram os dados armazenados em cache.

**Minha medida de detecção de alterações não dispara nenhuma atualização**

* Certifique-se de que a detecção de alterações esteja ativada para a página. Como essa configuração é definida por página, você precisa garantir que ela esteja ativada para cada página do relatório que deseja atualizar.
* Verifique se você carregou em um workspace com uma capacidade Premium anexada. Caso contrário, a detecção de alterações não funcionará.
* Se o relatório estiver em um workspace Premium, pergunte ao administrador se esse recurso está habilitado para a capacidade anexada. Além disso, certifique-se de que o intervalo mínimo de execução para a capacidade seja igual ou menor do que o intervalo do relatório.
* Caso tenha verificado todos os itens mencionados anteriormente, verifique no Power BI Desktop ou no modo de edição se a medida está sendo alterada. Para fazer isso, arraste-a para a tela e verifique se o valor é alterado. Caso contrário, a medida pode não ser uma boa opção para pesquisar alterações da fonte de dados.


## <a name="next-steps"></a>Próximas etapas

Para obter mais informações, confira estes tópicos:

* [Usar o DirectQuery no Power BI](../connect-data/desktop-directquery-about.md)
* [Usar modelos compostos no Power BI Desktop](../transform-model/desktop-composite-models.md)
* [Usar o Performance Analyzer para examinar o desempenho do elemento de relatório](desktop-performance-analyzer.md)
* [Como implantar e gerenciar capacidades do Power BI Premium](../guidance/whitepaper-powerbi-premium-deployment.md)
* [Fontes de dados no Power BI Desktop](../connect-data/desktop-data-sources.md)
* [Formatar e combinar dados no Power BI Desktop](../connect-data/desktop-shape-and-combine-data.md)
* [Conectar-se a pastas de trabalho do Excel no Power BI Desktop](../connect-data/desktop-connect-excel.md)   
* [Inserir dados diretamente no Power BI Desktop](../connect-data/desktop-enter-data-directly-into-desktop.md)   
