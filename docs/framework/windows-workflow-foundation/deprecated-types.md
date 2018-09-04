---
title: Tipi deprecati in Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: b25be26d4c0ad6c423b011cd7cad24a8728333f5
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43658899"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a>Tipi deprecati in Windows Workflow Foundation
In .NET 4 team del flusso di lavoro ha rilasciato un motore del flusso di lavoro totalmente nuovo nello spazio dei nomi <xref:System.Activities>. Con la versione di .NET 4.5 Beta la maggior parte dei tipi in "WF 3" vengono contrassegnati <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, e <xref:System.Workflow.Runtime> spazi dei nomi come obsoleto.  
  
## <a name="obsolete-namespaces-and-tools"></a>Spazi dei nomi e strumenti obsoleti  
 Gli assembly seguenti includono uno o più tipi pubblici che saranno deprecati:  
  
-   System.Workflow.Activities.dll  
  
-   System.Workflow.ComponentModel.dll  
  
-   System.Workflow.Runtime.dll  
  
-   System.WorkflowServices.dll  
  
-   Microsoft.Workflow.DebugController.dll  
  
-   Microsoft.Workflow.Compiler.exe  
  
-   Wfc.exe  
  
 Di conseguenza, i clienti che usano le API di WF 3 deprecate riceveranno avvisi di compilazione con un messaggio simile al seguente:  
  
 **Avviso BC40000: X è obsoleto: tipi di WF 3 sono deprecati. Usare WF 4.** I tipi verranno rimossi da .NET Framework in una versione futura, ma non è stato ancora determinato l'arco di tempo (non in 4.5). L'attuale passaggio intende comunicare la direttiva ai clienti concedendo loro il tempo sufficiente per passare al nuovo modello WF4. È, naturalmente, continuerà a supportare questi tipi di WF 3 con il [ciclo di vita del supporto Microsoft](https://aka.ms/MicrosoftSupportLifecycle). Le applicazioni in WF3 esistenti verranno eseguite senza problemi in .NET 4.5 e [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] supporterà le nuove e soluzioni esistenti basate su WF3.  
  
 I tipi relativi alle regole nello spazio dei nomi <xref:System.Workflow.Activities.Rules>, che non hanno una sostituzione in WF 4.5, non sono stati deprecati.  
  
 I clienti che desiderano eseguire la migrazione delle applicazioni a WF 4 possono trovare le informazioni nel [flusso di lavoro 4 Migration Guidance](migration-guidance.md).
