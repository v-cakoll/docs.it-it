---
ms.openlocfilehash: 97a92c6bce80b93e9a8bdd863bf881631eaffb27
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804684"
---
### <a name="workflowdesignerload-doesnt-remove-symbol-property"></a>WorkflowDesigner.Load non rimuove la proprietà del simbolo

|   |   |
|---|---|
|Dettagli|Se si usa .NET Framework 4.5 come destinazione in Progettazione flussi di lavoro e si carica un flusso di lavoro 3.5 riallocato con il metodo <xref:System.Activities.Presentation.WorkflowDesigner.Load>, viene generata un'eccezione <xref:System.Xaml.XamlDuplicateMemberException?displayProperty=name> durante il salvataggio del flusso di lavoro.|
|Suggerimento|Questo bug si manifesta solo quando si seleziona .NET Framework 4.5 come destinazione in Progettazione flussi di lavoro, quindi è possibile evitarlo impostando <code>WorkflowDesigner.Context.Services.GetService&lt;DesignerConfigurationService&gt;().TargetFrameworkName</code> su .NET Framework 4.0. In alternativa il problema può essere evitato usando il metodo <xref:System.Activities.Presentation.WorkflowDesigner.Load(System.String)> per caricare il flusso di lavoro, invece di <xref:System.Activities.Presentation.WorkflowDesigner.Load>.|
|Ambito|Principale|
|Versione|4.5|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Activities.Presentation.WorkflowDesigner.Load?displayProperty=nameWithType></li></ul>|

