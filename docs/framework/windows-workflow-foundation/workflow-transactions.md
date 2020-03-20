---
title: Transazioni del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 6081fb02-c0f2-483d-97b8-f3b7dc03011d
ms.openlocfilehash: 223c18195c8ffd0b51eb5dff77aa81953f6e47a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182679"
---
# <a name="workflow-transactions"></a><span data-ttu-id="6d1d0-102">Transazioni del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="6d1d0-102">Workflow Transactions</span></span>

<span data-ttu-id="6d1d0-103">In [!INCLUDE[wf1](../../../includes/wf1-md.md)] è disponibile il supporto per partecipare alle transazioni <xref:System.Transactions> tramite l'attività <xref:System.Activities.Statements.TransactionScope> per definire l'ambito di un'unità transazionale di lavoro.</span><span class="sxs-lookup"><span data-stu-id="6d1d0-103">[!INCLUDE[wf1](../../../includes/wf1-md.md)] provides support for participating in <xref:System.Transactions> transactions by using the <xref:System.Activities.Statements.TransactionScope> activity to scope a transacted unit of work.</span></span> <span data-ttu-id="6d1d0-104">Mentre l'oggetto <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> deve essere completato in modo esplicito, l'attività <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> effettua le chiamate in modo implicito sulla transazione in seguito al corretto completamento.</span><span class="sxs-lookup"><span data-stu-id="6d1d0-104">While the <xref:System.Transactions.TransactionScope?displayProperty=nameWithType> must be explicitly completed the <xref:System.Activities.Statements.TransactionScope?displayProperty=nameWithType> activity implicitly calls complete on the transaction upon successful completion.</span></span> <span data-ttu-id="6d1d0-105">Qualsiasi attività contenuta nell'elemento <xref:System.Activities.Statements.TransactionScope.Body%2A> dell'attività <xref:System.Activities.Statements.TransactionScope> partecipa alla transazione.</span><span class="sxs-lookup"><span data-stu-id="6d1d0-105">Any activities that are contained in the <xref:System.Activities.Statements.TransactionScope.Body%2A> of the <xref:System.Activities.Statements.TransactionScope> activity participate in the transaction.</span></span> <span data-ttu-id="6d1d0-106">WF può propagare transazioni in un flusso di lavoro tramite l'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="6d1d0-106">WF can to flow transactions into a workflow through the use of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="6d1d0-107">Analogamente all'attività <xref:System.Activities.Statements.TransactionScope>, qualsiasi attività contenuta nella proprietà <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> partecipa alla transazione.</span><span class="sxs-lookup"><span data-stu-id="6d1d0-107">Like the <xref:System.Activities.Statements.TransactionScope> activity, any activity contained in the <xref:System.ServiceModel.Activities.TransactedReceiveScope.Body%2A> participates in the transaction.</span></span> <span data-ttu-id="6d1d0-108">WF assicura che nelle attività che dipendono dall'oggetto <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> possano essere usati entrambi gli oggetti <xref:System.Activities.Statements.TransactionScope> e <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span><span class="sxs-lookup"><span data-stu-id="6d1d0-108">WF ensures that activities dependent on <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType> works with both <xref:System.Activities.Statements.TransactionScope> and <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="6d1d0-109">Se le attività fornite dal sistema non soddisfano tutti i requisiti, possono essere compilate attività personalizzate tramite l'oggetto <xref:System.Activities.RuntimeTransactionHandle> per abilitare scenari di controllo di transazioni e flussi avanzati.</span><span class="sxs-lookup"><span data-stu-id="6d1d0-109">If the system-provided activities do not address all requirements, custom activities can be built using the <xref:System.Activities.RuntimeTransactionHandle> to enable advanced flow and transaction control scenarios.</span></span>  
  
<span data-ttu-id="6d1d0-110">Nell'esempio seguente viene creato un <xref:System.Activities.Statements.Sequence> flusso di lavoro costituito da un'attività che contiene attività figlio che includono un'attività. <xref:System.Activities.Statements.TransactionScope></span><span class="sxs-lookup"><span data-stu-id="6d1d0-110">In the following example, a workflow is constructed consisting of a <xref:System.Activities.Statements.Sequence> activity that contains child activities including a <xref:System.Activities.Statements.TransactionScope> activity.</span></span> <span data-ttu-id="6d1d0-111">Le attività <xref:System.Activities.Statements.TransactionScope.Body%2A> di <xref:System.Activities.Statements.TransactionScope> vengono eseguite nella transazione inizializzata dall'attività <xref:System.Activities.Statements.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="6d1d0-111">The <xref:System.Activities.Statements.TransactionScope.Body%2A> activities of the <xref:System.Activities.Statements.TransactionScope> execute under the transaction initialized by the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
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
  
<span data-ttu-id="6d1d0-112">Per ulteriori informazioni, <xref:System.ServiceModel.Activities.TransactedReceiveScope>vedere Informazioni sull'utilizzo di , vedere [Flusso di transazioni all'esterno e all'esterno di Servizi flusso di](../wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md)lavoro .</span><span class="sxs-lookup"><span data-stu-id="6d1d0-112">For more information, see about using <xref:System.ServiceModel.Activities.TransactedReceiveScope>, see [Flowing Transactions into and out of Workflow Services](../wcf/feature-details/flowing-transactions-into-and-out-of-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d1d0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d1d0-113">See also</span></span>

- <xref:System.Activities.Statements.TransactionScope>
- <xref:System.Transactions.TransactionScope>
- <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>
