---
title: Tipi deprecati in Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: d41bf147cd079a3d6d3714da5595732de3dcb7de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774049"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a>Tipi deprecati in Windows Workflow Foundation
In .NET 4 team del flusso di lavoro ha rilasciato un motore del flusso di lavoro totalmente nuovo nello spazio dei nomi <xref:System.Activities>. Con la versione di .NET 4.5 Beta la maggior parte dei tipi in "WF 3" vengono contrassegnati <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, e <xref:System.Workflow.Runtime> spazi dei nomi come obsoleto.  
  
## <a name="obsolete-namespaces-and-tools"></a>Spazi dei nomi e strumenti obsoleti  
 Gli assembly seguenti includono uno o più tipi pubblici che saranno deprecati:  
  
- System.Workflow.Activities.dll  
  
- System.Workflow.ComponentModel.dll  
  
- System.Workflow.Runtime.dll  
  
- System.WorkflowServices.dll  
  
- Microsoft.Workflow.DebugController.dll  
  
- Microsoft.Workflow.Compiler.exe  
  
- Wfc.exe  
  
 Di conseguenza, i clienti che usano le API di WF 3 deprecate riceveranno avvisi di compilazione con un messaggio simile al seguente:  
  
 **Avviso BC40000: X è obsoleto: WF 3 sono stati deprecati. Usare WF 4.** I tipi verranno rimossi da .NET Framework in una versione futura, ma non è stato ancora determinato l'arco di tempo (non in 4.5). L'attuale passaggio intende comunicare la direttiva ai clienti concedendo loro il tempo sufficiente per passare al nuovo modello WF4. È, naturalmente, continuerà a supportare questi tipi di WF 3 con il [ciclo di vita del supporto Microsoft](https://aka.ms/MicrosoftSupportLifecycle). Le applicazioni WF3 esistenti verranno eseguite senza problemi in .NET 4.5 e Visual Studio 2012 supporterà le soluzioni basate su WF3 nuove ed esistenti.  
  
 I tipi relativi alle regole nello spazio dei nomi <xref:System.Workflow.Activities.Rules>, che non hanno una sostituzione in WF 4.5, non sono stati deprecati.  
  
 I clienti che desiderano eseguire la migrazione delle applicazioni a WF 4 possono trovare le informazioni nel [flusso di lavoro 4 Migration Guidance](migration-guidance.md).
