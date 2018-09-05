---
title: Utilizzo dell'attività CancellationScope
ms.date: 03/30/2017
ms.assetid: 39c5c338-b316-43d6-b7fe-a543281dd1ec
ms.openlocfilehash: 82d44fff869f207c09dc7685fc3470630e001a59
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43731521"
---
# <a name="using-cancellationscope"></a>Utilizzo dell'attività CancellationScope
Nell'esempio viene illustrato come usare l'attività <xref:System.Activities.Statements.CancellationScope> per annullare il lavoro in un'applicazione.  
  
 Molti componenti e servizi di livello intermedio si basano sul noto costrutto di programmazione delle transazioni per gestire l'annullamento.  Esistono tuttavia molte situazioni nelle quali è necessario annullare il lavoro che non può essere eseguito in una transazione.  Usare l'annullamento è più difficile che usare le transazioni perché il lavoro da annullare deve prima essere rilevato. [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] semplifica questa operazione fornendo un'attività <xref:System.Activities.Statements.CancellationScope>.  
  
 È possibile attivare l'annullamento dall'interno un'attività o dall'elemento padre dell'attività.  Le attività figlio sono pianificate dall'attività padre (ad esempio <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Parallel>, <xref:System.Activities.Statements.Flowchart> o da una CompositeActivity personalizzata).  L'attività padre può annullare le attività figlio per qualsiasi motivo.  Ad esempio, un'attività <xref:System.Activities.Statements.Parallel> con tre rami figlio annullerà i rami figlio restanti quando completa un ramo e l'espressione <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> restituisce `true`. Il flusso di lavoro può essere annullato anche esternamente dall'applicazione host chiamando <xref:System.Activities.WorkflowApplication.Cancel%2A>.  
  
 Per usare l'attività <xref:System.Activities.Statements.CancellationScope>, inserire il lavoro che deve essere annullato nella proprietà <xref:System.Activities.Statements.CancellationScope.Body%2A> e inserire il lavoro eseguito dopo l'annullamento nella proprietà <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>.  
  
 In questo esempio viene illustrato l'annullamento di un'attività dall'interno dell'attività stessa.  
  
 Lo scenario usato nell'esempio per illustrare l'attività <xref:System.Activities.Statements.CancellationScope> è un cliente che desidera acquistare il prima possibile un biglietto per Miami. Due agenzie di viaggio desiderano concludere l'affare. Nell'esempio vengono usati due oggetti <xref:System.Activities.Statements.CancellationScope> all'interno di un'attività <xref:System.Activities.Statements.Parallel> per modellare questa logica di business. L'oggetto <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> dell'attività <xref:System.Activities.Statements.Parallel> viene impostato su `true`. Poiché <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> viene controllato dopo il completamento di qualsiasi ramo, questo farà in modo che il ramo restante venga annullato dopo il completamento del primo ramo. L'acquisto del biglietto viene richiesto dall'applicazione client a entrambe le agenzie e quando la prima conferma che il biglietto è stato acquistato, l'ordine all'altra agenzia viene annullato automaticamente.  
  
## <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione CancelationScopeXAML.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere CTRL+F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\CancellationScope`