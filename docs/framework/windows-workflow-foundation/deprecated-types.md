---
title: Tipi deprecati in Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: 899d21f23c0500a1df01916d1da210b2f9bea95b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a>Tipi deprecati in Windows Workflow Foundation
In .NET 4 team del flusso di lavoro ha rilasciato un motore del flusso di lavoro totalmente nuovo nello spazio dei nomi <xref:System.Activities>. La maggior parte dei tipi in "WF 3" vengono contrassegnati con la versione di .NET 4.5 Beta <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, e <xref:System.Workflow.Runtime> gli spazi dei nomi come obsoleto.  
  
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
  
 **Avviso BC40000: X è obsoleto: tipi di WF 3 sono deprecati. Usare WF 4.** I tipi verranno rimossi da .NET Framework in una versione futura, ma non è stato ancora determinato l'arco di tempo (non in 4.5). L'attuale passaggio intende comunicare la direttiva ai clienti concedendo loro il tempo sufficiente per passare al nuovo modello WF4. È, naturalmente, continuerà a supportare questi tipi in WF 3 il [ciclo di vita del supporto Microsoft](http://aka.ms/MicrosoftSupportLifecycle). Le applicazioni in WF3 esistenti verranno eseguite senza problemi in .NET 4.5 e [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] supporterà le nuove e soluzioni esistenti basate su WF3.  
  
 I tipi relativi alle regole nello spazio dei nomi <xref:System.Workflow.Activities.Rules>, che non hanno una sostituzione in WF 4.5, non sono stati deprecati.  
  
 I clienti che desiderano eseguire la migrazione delle applicazioni a WF 4 troverà la Guida in linea di [Guida alla migrazione del flusso di lavoro 4](migration-guidance.md).
