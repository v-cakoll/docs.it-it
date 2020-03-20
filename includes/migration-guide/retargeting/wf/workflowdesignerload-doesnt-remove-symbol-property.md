---
ms.openlocfilehash: 19c613bf48479cb1e52531a4d6594db8ad89b8f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804684"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a>WorkflowDesigner.Load non rimuove la proprietà del simbolo

|   |   |
|---|---|
|Dettagli|Se si usa .NET Framework 4.5 come destinazione in Progettazione flussi di lavoro e si carica un flusso di lavoro 3.5 riallocato con il metodo <xref:System.Activities.Presentation.WorkflowDesigner.Load>, viene generata un'eccezione <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> durante il salvataggio del flusso di lavoro.|
|Suggerimento|Questo bug si manifesta solo quando si seleziona .NET Framework 4.5 come destinazione in Progettazione flussi di lavoro, quindi è possibile evitarlo impostando <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> su .NET Framework 4.0. In alternativa il problema può essere evitato usando il metodo <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> per caricare il flusso di lavoro, invece di <xref:System.Activities.Presentation.WorkflowDesigner.Load>.|
|Scope|Principale|
|Versione|4.5|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType></li></ul>|
