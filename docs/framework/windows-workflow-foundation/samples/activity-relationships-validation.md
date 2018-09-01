---
title: Convalida di relazioni tra attività
ms.date: 03/30/2017
ms.assetid: 6f11a34e-ed67-4bce-88ce-7e96bbb4d052
ms.openlocfilehash: 50f08118fb5ad4d9b8fe809e7ab3cc5d57f28149
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43394685"
---
# <a name="activity-relationships-validation"></a>Convalida di relazioni tra attività
Il presente esempio è costituito da tre attività, `CreateCity`, `CreateState` e `CreateCountry`. `CreateCity` deve trovarsi all'interno di un'attività `CreateState` e `CreateState` deve trovarsi all'interno di un'attività `CreateCountry`. Ai fini di questo esempio, la logica di convalida è nel codice per l'attività `CreateState` e in XAML per l'attività `CreateCity`. Entrambi i vincoli presentano lo stesso comportamento.  
  
 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] fornisce le tre attività di supporto seguenti che consentono allo sviluppatore di convalidare relazioni tra attività.  
  
 <xref:System.Activities.Validation.GetParentChain>  
 Viene fornita la raccolta di tutte le attività che appartengono all'elemento padre del nodo corrente.  
  
 <xref:System.Activities.Validation.GetChildSubtree>  
 Viene fornita la raccolta di tutte le attività che appartengono al sottoalbero, escluso il nodo corrente.  
  
 <xref:System.Activities.Validation.GetWorkflowTree>  
 Viene fornita la raccolta di tutte le attività nello stesso albero del nodo corrente.  
  
 Nell'esempio, un'attività <xref:System.Activities.Statements.ForEach%601> viene usata per esaminare la raccolta restituita da <xref:System.Activities.Validation.GetParentChain>. Per ogni elemento nella raccolta, il tipo viene confrontato con `CreateCountry` (o `CreateState` se è in corso la convalida di `CreateCity`) e quando viene trovata una corrispondenza il flag del risultato viene impostato su `true`. Infine, viene usato <xref:System.Activities.Validation.AssertValidation> per generare un errore di convalida se il flag del risultato viene impostato su `false`.  
  
### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire la soluzione di esempio ContainmentValidation.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compilare la soluzione.  
  
3.  Premere CTRL+F5 per avviare il programma.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ActivityRelationships`
