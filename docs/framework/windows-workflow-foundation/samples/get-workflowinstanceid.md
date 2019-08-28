---
title: Ottenere WorkflowInstanceId
ms.date: 03/30/2017
ms.assetid: bd7eea3b-1c28-4b84-9a67-003bc553aa81
ms.openlocfilehash: 73fee4376b1abe29620bfae05bbd96fccf7b17c4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70038145"
---
# <a name="get-workflowinstanceid"></a>Ottenere WorkflowInstanceId
In questo esempio viene illustrato come usare l'attività personalizzata, `GetWorkflowInstanceId`, per restituire l'ID istanza del flusso di lavoro.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Sviluppo dell'attività personalizzata, come accedere all'istanza del flusso di lavoro.  
  
## <a name="discussion"></a>Discussione  
 L'acquisizione dell'ID istanza di un flusso di lavoro in esecuzione richiede che venga scritto codice. Se si desidera scrivere un flusso di lavoro completamente dichiarativo, è necessaria un'attività che possa restituire l'ID istanza del flusso di lavoro in modo che sia possibile fare riferimento all'attività nel flusso di lavoro per fornire una creazione di flussi di lavoro completamente dichiarativa. Molti scenari richiedono l'accesso all'ID istanza: alcuni esempi sono per la registrazione o il controllo degli scopi o per eseguire la correlazione a livello di applicazione fornendo di nuovo l'ID istanza a un client per l'associazione futura (ad esempio, tramite questa attività in un'attività SendReply).  
  
 L'oggetto `GetWorkflowInstanceId` viene implementato come oggetto <xref:System.Activities.CodeActivity%601> perché deve restituire un valore di tipo <xref:System.Guid> e deve disporre dell'accesso all'oggetto <xref:System.Activities.CodeActivityContext> per l'acquisizione dell'ID istanza del flusso di lavoro. L'implementazione è abbastanza semplice.  
  
```  
public sealed class GetWorkflowInstanceId : CodeActivity<Guid>  
{  
protected override Guid Execute(CodeActivityContext context)  
        {  
            return context.WorkflowInstanceId;  
        }  
}  
```  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\GetWorkflowInstanceId`
