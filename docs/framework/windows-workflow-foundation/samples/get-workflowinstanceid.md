---
title: Ottenere WorkflowInstanceId
ms.date: 03/30/2017
ms.assetid: bd7eea3b-1c28-4b84-9a67-003bc553aa81
ms.openlocfilehash: 8cb83fcf15b814b0ca6f7f95f1a9b8eec70185cb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142732"
---
# <a name="get-workflowinstanceid"></a>Ottenere WorkflowInstanceId
In questo esempio viene illustrato come usare l'attività personalizzata, `GetWorkflowInstanceId`, per restituire l'ID istanza del flusso di lavoro.  
  
## <a name="demonstrates"></a>Dimostra  
 Sviluppo dell'attività personalizzata, come accedere all'istanza del flusso di lavoro.  
  
## <a name="discussion"></a>Discussione  
 L'acquisizione dell'ID istanza di un flusso di lavoro in esecuzione richiede che venga scritto codice. Se si desidera scrivere un flusso di lavoro completamente dichiarativo, è necessaria un'attività che possa restituire l'ID istanza del flusso di lavoro in modo che sia possibile fare riferimento all'attività nel flusso di lavoro per fornire una creazione di flussi di lavoro completamente dichiarativa. Molti scenari richiedono l'accesso all'ID istanza: alcuni esempi sono per la registrazione o il controllo degli scopi o per eseguire la correlazione a livello di applicazione fornendo di nuovo l'ID istanza a un client per l'associazione futura (ad esempio, tramite questa attività in un'attività SendReply).  
  
 L'oggetto `GetWorkflowInstanceId` viene implementato come oggetto <xref:System.Activities.CodeActivity%601> perché deve restituire un valore di tipo <xref:System.Guid> e deve disporre dell'accesso all'oggetto <xref:System.Activities.CodeActivityContext> per l'acquisizione dell'ID istanza del flusso di lavoro. L'implementazione è abbastanza semplice.  
  
```csharp  
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
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\GetWorkflowInstanceId`
