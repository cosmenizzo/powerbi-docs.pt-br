---
title: Cmdlets do PowerShell, APIs REST e bibliotecas de clientes .NET para administradores
description: Saiba mais sobre as maneiras de administrar o Power BI por meio de scripts e APIs de programação.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: c26d169a4c8ef876d1fe92e4967b07c982f510db
ms.sourcegitcommit: 9350f994b7f18b0a52a2e9f8f8f8e472c342ea42
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90856865"
---
# <a name="powershell-cmdlets-rest-apis-and-net-client-library-for-power-bi-administration"></a>Cmdlets do PowerShell, APIs REST e biblioteca de clientes .NET para administração do Power BI
O Power BI permite aos administradores fazer scripts de tarefas comuns com os cmdlets do PowerShell. Ele também expõe APIs REST e fornece uma biblioteca de clientes .NET para o desenvolvimento de soluções administrativas. Este tópico mostra uma lista de cmdlets, bem como as APIs e o ponto de extremidade da API REST. Para obter mais informações, veja:

- [Download](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) e [documentação](/powershell/power-bi/overview?view=powerbi-ps) do PowerShell
- [Documentação](/rest/api/power-bi/admin) da API REST
- [Download](https://www.nuget.org/packages/Microsoft.PowerBI.Api/) da biblioteca de clientes .NET

> Os cmdlets abaixo devem ser chamados com `-Scope Organization` para operar no locatário para administração.

| **Nome do cmdlet** | **Aliases** | **API** | **Ponto de extremidade da API REST** | **Descrição** |
| --- | --- | --- | --- | --- |
| `Get-PowerBIDatasource` | N/A | `Datasets_GetDataSourcesAsAdmin` | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Obtém as fontes de dados para um determinado conjunto de dados. |
| `Get-PowerBIDataset` | N/A | `Datasets_GetDatasetsAsAdmin` | /v1.0/myorg/admin/datasets | Obtém a lista completa de conjuntos de dados em um locatário do Power BI. |
| `Get-PowerBIWorkspace` | `Get-PowerBIGroup` | `Groups_GetGroupsAsAdmin` | /v1.0/myorg/admin/groups | Obtém a lista completa de workspaces em um locatário do Power BI. |
| `Add-PowerBIWorkspaceUser` | `Add-PowerBIGroupUser` | `Groups_AddUserAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/users | Adiciona um usuário como um membro a um determinado workspace. |
| `Remove-PowerBIWorkspaceUser` | `Remove-PowerBIGroupUser` | `Groups_DeleteUserAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Remove um usuário da lista de membros de um determinado workspace. |
| `Restore-PowerBIWorkspace` |`Restore-PowerBIGroup` | `Groups_RestoreDeletedGroupAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/restore | Restaura um workspace excluído. |
| `Set-PowerBIWorkspace` |`Set-PowerBIGroup` | `Groups_UpdateGroupAsAdmin` | /v1.0/myorg/admin/groups/{groupId} | Atualiza as propriedades de um determinado workspace. |
| `Get-PowerBIDataset -WorkspaceId` | N/A | `Groups_GetDatasetsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/datasets | Obtém os conjuntos de dados dentro de um determinado workspace. |
| `Get-PowerBIReport` | N/A | `Reports_GetReportsAsAdmin` | /v1.0/myorg/admin/reports | Obtém a lista completa de relatórios em um locatário do Power BI. |
| `Get-PowerBIDashboard` | N/A | `Dashboards_GetDashboardsAsAdmin` | /v1.0/myorg/admin/dashboards | Obtém a lista completa de dashboards em um locatário do Power BI. |
| `Get-PowerBIDashboard -WorkspaceId` | N/A | `Groups_GetDashboardsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Obtém os dashboards dentro de um determinado workspace. |
| `Get-PowerBITile` | `Get-PowerBIDashboardTile` | `Dashboards_GetTilesAsAdmin` | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Obtém os blocos de um determinado dashboard. |
| `Get-PowerBIReport` | N/A | `Groups_GetReportsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/reports | Obtém os relatórios dentro de um determinado workspace. |
| `Get-PowerBIImport` | N/A | `Imports_GetImportsAsAdmin` | /v1.0/myorg/admin/imports | Obtém a lista completa de importações em um locatário do Power BI. |
| `Connect-PowerBIServiceAccount` | `Login-PowerBI` &  `Login-PowerBIServiceAccount` | N/A | N/A | Faça logon no Power BI e inicie uma sessão. |
| `Disconnect-PowerBIServiceAccount` | `Logout-PowerBI` & `Logout-PowerBIServiceAccount` | N/A | N/A | Faça logoff do Power BI e feche a sessão existente. |
| `Invoke-PowerBIRestMethod`| N/A | N/A | N/A | Envie chamadas arbitrárias da API REST ao Power BI. |
| `Get-PowerBIAccessToken`| N/A | N/A | N/A | Obtenha o token de acesso do Power BI em uma sessão. |
| `Resolve-PowerBIError`| N/A | N/A | N/A | Obtenha informações detalhadas do erro para chamadas de cmdlet sem êxito. |