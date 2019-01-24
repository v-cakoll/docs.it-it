---
title: Transazioni del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
ms.openlocfilehash: 061cebb6791ada9e3e64097a6490b1e2b4736839
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624209"
---
# <a name="workflow-transactions"></a>Transazioni del flusso di lavoro

In [!INCLUDE[wf1](../../../includes/wf1-md.md)] è disponibile il supporto per partecipare alle transazioni <xref:System.Transactions> tramite l'attività <xref:System.Activities.Statements.TransactionScope> per definire l'ambito di un'unità transazionale di lavoro. Mentre l'oggetto <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> deve essere completato in modo esplicito, l'attività <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> effettua le chiamate in modo implicito sulla transazione in seguito al corretto completamento. Qualsiasi attività contenuta nell'elemento <xref:System.Activities.Statements.TransactionScope.Body%2A> dell'attività <xref:System.Activities.Statements.TransactionScope> partecipa alla transazione. WF può propagare transazioni in un flusso di lavoro tramite l'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Analogamente all'attività <xref:System.Activities.Statements.TransactionScope>, qualsiasi attività contenuta nella proprietà <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> partecipa alla transazione. WF assicura che nelle attività che dipendono dall'oggetto <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> possano essere usati entrambi gli oggetti <xref:System.Activities.Statements.TransactionScope> e <xref:System.ServiceModel.Activities.TransactedReceiveScope>. Se le attività fornite dal sistema non soddisfano tutti i requisiti, possono essere compilate attività personalizzate tramite l'oggetto <xref:System.Activities.RuntimeTransactionHandle> per abilitare scenari di controllo di transazioni e flussi avanzati.  
  
Nell'esempio seguente viene creato un flusso di lavoro costituito da un <xref:System.Activities.Statements.Sequence> attività che contiene attività figlio inclusa un' <xref:System.Activities.Statements.TransactionScope> attività. Le attività <xref:System.Activities.Statements.TransactionScope.Body%2A> di <xref:System.Activities.Statements.TransactionScope> vengono eseguite nella transazione inizializzata dall'attività <xref:System.Activities.Statements.TransactionScope>.  
  
```csharp  
static Activity ScenarioOne()  
{  
    return new Sequence  
    {  
        Activities =  
        {  
            new WriteLine { Text = "    Begin workflow" },  
  
            new TransactionScope  
            {  
                Body = new Sequence  
                {  
                    Activities =   
                    {  
                        new WriteLine { Text = "    Begin TransactionScope" },  
  
                        new PrintTransactionId(),  
  
                        new TransactionScopeTest(),  
  
                        new WriteLine { Text = "    End TransactionScope" },  
                    },  
                },  
            },  
  
            new WriteLine { Text = "    End workflow" },  
        }  
    };  
}  
```  
  
Per altre informazioni, vedere l'argomento sull'uso <xref:System.ServiceModel.Activities.TransactedReceiveScope>, vedere [transazioni che passano da e verso i servizi del flusso di lavoro](../../../docs/framework/wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Activities.Statements.TransactionScope>
- <xref:System.Transactions.TransactionScope>
- <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>
